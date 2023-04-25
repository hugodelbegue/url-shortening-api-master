<script setup>
import Logo from '@/components/Logo.vue';
import Button from '@/components/Button.vue';
</script>

<template>
    <header>
        <div class="layout_header body_size">
            <Logo color="#34313D" />
            <nav class="burger_menu">
                <input @change="toggleMenu" type="checkbox" id="burger">
                <label for="burger">
                    <div class="icon_menu"></div>
                </label>
                <div class="burger_links hide" ref="links">
                    <ul>
                        <li>Features</li>
                        <li>Pricing</li>
                        <li>Resources</li>
                        <hr>
                        <li>Login</li>
                        <li>
                            <Button text="Sign Up" />
                        </li>
                    </ul>
                </div>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    methods: {
        toggleMenu() {
            const { links } = this.$refs;
            if (links.classList.contains('hide')) {
                links.style.display = "flex";
                links.classList.remove('hide');
                links.classList.add('show');
            } else {
                links.classList.remove('show');
                links.classList.add('hide');
                setTimeout(() => {
                    links.style.display = "none";
                }, 500);
            }
            document.body.classList.toggle('hidden');
        }
    }
}
</script>

<style lang="scss" scoped>
header {
    --size-burger: 30px;
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
    padding-top: var(--endpoint-padding);
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

.burger_links {
    background: var(--background-tersiary);
    z-index: 1;
    flex-direction: column;
    text-align: center;
    position: fixed;
    top: 6rem;
    left: 0;
    padding: calc(var(--body-padding) * 2) var(--body-padding);
    margin-left: max(var(--body-padding), calc(50% - var(--mobile) / 2));
    margin-right: max(var(--body-padding), calc(50% - var(--mobile) / 2));
    border-radius: 12px;
    width: -webkit-fill-available;

    ul {
        display: flex;
        flex-direction: column;
        gap: 1.8em;
    }

    li {
        cursor: pointer;
        color: var(--color-title-light);

        button {
            width: 100%;
            font-size: 1em;
        }
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