<template>
    <button>
        {{ text }}
    </button>
</template>

<script setup>
defineProps({
    text: {
        type: String,
    }
})
</script>

<style lang="scss" scoped>
button {
    cursor: pointer;
    background: var(--background-button);
    border: 4px solid var(--background-button);
    color: var(--color-title-light);
    border-radius: 50px;
    padding: .8em 2.2em;
    font-size: 1.4rem;
    font-weight: var(--weight-bold);
    line-height: 1;
    transition: background .2s ease;

    &:hover {
        background: var(--background-button-active);
    }

    &:active {
        background: var(--background-button-active);
    }
}
</style>