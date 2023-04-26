<script setup>
import Logo from '@/components/Logo.vue';
import Button from '@/components/Button.vue';
</script>

<template>
    <header>
        <div class="layout_header body_size">
            <Logo color="#34313D" />
            <nav class="nav_desktop">
                <ul>
                    <li>Features</li>
                    <li>Pricing</li>
                    <li>Resources</li>
                </ul>
                <ul>
                    <li>Login</li>
                    <li>
                        <Button text="Sign&nbsp;Up" />
                    </li>
                </ul>
            </nav>
            <nav class="nav_mobile">
                <input @change="openMenu" type="checkbox" id="burger">
                <label ref="burger" for="burger">
                    <div class="icon_menu"></div>
                </label>
                <div class="burger_links" ref="links">
                    <ul>
                        <li>Features</li>
                        <li>Pricing</li>
                        <li>Resources</li>
                        <hr>
                        <li>Login</li>
                        <li>
                            <Button text="Sign&nbsp;Up" />
                        </li>
                    </ul>
                </div>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    mounted() {
        const { links, burger } = this.$refs;
        function clickOut(event) {
            if (!links.contains(event.target) && links.classList.contains('show')) {
                links.classList.remove('show');
                links.classList.add('hide');
                burger.style.pointerEvents = "";
                document.body.classList.remove('hidden');
                setTimeout(() => {
                    links.style.display = "none";
                }, 500);
            }
        }
        document.addEventListener("click", clickOut);
    },
    methods: {
        openMenu() {
            const { links, burger } = this.$refs;
            if (links.classList.contains('hide') || !links.classList.contains('show')) {
                links.style.display = "flex";
                links.classList.remove('hide');
                links.classList.add('show');
                burger.style.pointerEvents = "none";
                document.body.classList.add('hidden');
            }
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/responsive.scss';

header {
    --size-burger: 30px;
    --space-between-links: 1.8em;
    --color-hover: var(--background-button);

    @media #{$navDesktop} {
        --color-hover: var(--very-dark-blue);
    }
}

svg {
    width: 150px;
}

input[type="checkbox"] {
    display: none;
}

label {
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    width: var(--size-burger);
    height: auto;
    aspect-ratio: 1/1;
}

hr {
    border-color: var(--background-secondary);
    background: var(--background-secondary);
    opacity: .4;
}

.layout_header {
    display: flex;
    place-content: space-between;
    place-items: center;
    padding-top: var(--endpoint);

    @media #{$navDesktop} {
        gap: 3em;
    }
}

.icon_menu,
.icon_menu::before,
.icon_menu::after {
    content: "";
    position: relative;
    display: flex;
    background: var(--color-text);
    width: 100%;
    height: 4px;
}

.icon_menu::before {
    position: absolute;
    top: 12px;
}

.icon_menu::after {
    position: absolute;
    bottom: 12px;
}

.nav_mobile {
    display: flex;

    @media #{$navDesktop} {
        display: none;
    }
}

.burger_links {
    background: var(--background-tersiary);
    z-index: 1;
    display: none;
    flex-direction: column;
    text-align: center;
    position: fixed;
    top: 6.4rem;
    left: 0;
    padding: var(--side-double) var(--side);
    margin-left: var(--body-side);
    margin-right: var(--body-side);
    border-radius: 12px;
    width: -webkit-fill-available;

    ul {
        display: flex;
        flex-direction: column;
        gap: var(--space-between-links);
    }

    li {
        color: var(--color-title-light);
    }
}

.nav_desktop {
    display: none;
    place-content: space-between;
    place-items: center;
    width: 100%;

    @media #{$navDesktop} {
        display: flex;
    }

    ul {
        display: flex;
        place-items: center;
        gap: var(--space-between-links);
    }

    li {

        &:hover,
        &:active {
            color: var(--color-hover) !important;
        }
    }

    button {
        padding: 1.1em 1.6em;
    }
}

// toggle menu
.show {
    animation: rollOut .5s ease both;
}

.hide {
    animation: rollIn .5s ease both;
}

@keyframes rollOut {
    from {
        transform: translateY(-150%);
    }

    to {
        transform: translateY(0%);
    }
}

@keyframes rollIn {
    from {
        transform: translateY(0%);
    }

    to {
        transform: translateY(-150%);
    }
}
</style>