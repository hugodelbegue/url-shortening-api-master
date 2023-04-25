<script setup>
import Button from './Button.vue';
</script>

<template>
    <form @submit.prevent="submitForm" class="shorten">
        <div class="input_form">
            <input :class="error" type="text" placeholder="Shorten a link here...">
            <p v-if="false" class="error">Please ass a link</p>
        </div>
        <Button text="Shorten It!" />
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
form {
    --background-input: #fff;
    --size-font-shorten: calc(var(--font-size) + 3px);
    --angles: 7px;
}

.shorten {
    position: absolute;
    top: calc(-185px / 2);
    display: flex;
    flex-direction: column;
    gap: var(--body-padding);
    background-color: var(--background-tersiary);
    background-image: url(@/assets/images/bg-shorten-mobile.svg);
    background-position-y: 300%;
    background-repeat: no-repeat;
    background-size: cover;
    padding: var(--body-padding);
    margin-left: var(--side-padding);
    margin-right: var(--side-padding);
    border-radius: 12px;
    width: -webkit-fill-available;
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