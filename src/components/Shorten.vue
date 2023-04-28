<script setup>
import Button from './Button.vue';
import Short from './Short.vue';
</script>

<template>
    <form @submit.prevent="submitForm" class="shorten">
        <div class="input_form">
            <input :class="empty" type="text" placeholder="Shorten a link here...">
            <p v-if="this.error" class="error">Please ass a link</p>
        </div>
        <Button text="Shorten&nbsp;It!" />
    </form>
    <div :class="space" class="list">
        <Short v-for="link in listLinks" :key="link" :class="copied" :full="link.full" :short="link.short"
            :button="link.button" />
    </div>
</template>

<script>
export default {
    data() {
        return {
            listLinks: {
                1: {
                    full: "https://www.frontendmentor.io",
                    short: "https://rel.ink/k4iKyk",
                    button: "Copy"
                },
                2: {
                    full: "https://www.frontendmentor.io",
                    short: "https://rel.ink/k4iKyk",
                    button: "Copied!"
                },
                3: {
                    full: "https://www.frontendmentor.io",
                    short: "https://rel.ink/k4iKyk",
                    button: "Copy"
                }
            },
            error: false,
        }
    },
    computed: {
        empty() {
            return {
                border_error: this.error
            }
        },
        space() {
            return {
                space: this.error
            }
        },
        copied() {
            return {
                copied: true
            }
        },
        submitForm() {
            console.log('hello');
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/responsive.scss';

form {
    --background-input: #fff;
    --size-font-shorten: calc(var(--font-size) + 3px);
    --padding: var(--side);
    --middle: calc(-185px / 2);
    --between: var(--side);

    @media #{$tabletScreen} {
        --padding: 3rem 4rem;
        --middle: calc(-157px / 2);
        --between: 1.4rem;
    }
}

.shorten {
    position: absolute;
    top: var(--middle);
    display: flex;
    flex-direction: column;
    gap: var(--side);
    background-color: var(--background-tersiary);
    background-image: url(@/assets/images/bg-shorten-mobile.svg);
    background-position-y: top;
    background-position-x: right;
    background-size: 80% 80%;
    background-repeat: no-repeat;
    padding: var(--padding);
    margin-left: var(--body-side);
    margin-right: var(--body-side);
    border-radius: calc(var(--angles-block) + 5px);
    width: -webkit-fill-available;

    @media #{$tabletScreen} {
        flex-direction: row;
        background-image: url(@/assets/images/bg-shorten-desktop.svg);
        background-position: center;
        background-size: cover;
    }
}

.input_form {
    @media #{$tabletScreen} {
        width: 100%;
    }
}

input[type="text"] {
    background: var(--background-input);
    border: 4px solid var(--background-input);
    border-radius: var(--angles-block);
    padding: .93em;
    display: flex;
    place-items: center;
    line-height: 0;
    width: 100%;
    font-size: 1em;

    &::placeholder {
        font-size: var(--size-font-shorten);
    }
}

button {
    font-size: var(--size-font-shorten);
    border-radius: var(--angles-block);
}

.list {
    --space-links: 1.8rem;
    width: 100%;
    margin-top: var(--space-links);
    display: flex;
    flex-direction: column;
    gap: var(--space-links);
}

// class
.error {
    color: var(--color-error);
    font-size: .8em;
    font-weight: var(--weight-regular);
    font-style: italic;
    text-align: left;
    margin-top: .3em;

    @media #{$tabletScreen} {
        position: absolute;
    }
}

.border_error {
    border-color: var(--color-error) !important;

    &::placeholder {
        color: var(--color-error) !important;
    }
}

.space {
    margin-top: calc(var(--space-links) + 2rem);

    @media #{$tabletScreen} {
        margin-top: var(--space-links);
    }
}

.copied:deep(button) {
    --color-copied: var(--very-dark-blue);
    background-color: var(--color-copied);
    border-color: var(--color-copied);
    pointer-events: none;
}
</style>