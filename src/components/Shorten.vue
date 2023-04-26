<script setup>
import Button from './Button.vue';
</script>

<template>
    <form @submit.prevent="submitForm" class="shorten">
        <div class="input_form">
            <input :class="error" type="text" placeholder="Shorten a link here...">
            <p v-if="false" class="error">Please ass a link</p>
        </div>
        <Button text="Shorten&nbsp;It!" />
    </form>
</template>

<script>
export default {
    computed: {
        error() {
            return {
                border_error: false
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
    --angles: 7px;
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
    border-radius: 12px;
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
    border-radius: var(--angles);
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
    border-radius: var(--angles);
}

.error {
    color: var(--color-error);
    font-size: .8em;
    font-weight: var(--weight-regular);
    font-style: italic;
    text-align: left;
    margin-top: .3em;
}

.border_error {
    border-color: var(--color-error) !important;

    &::placeholder {
        color: var(--color-error) !important;
    }
}
</style>