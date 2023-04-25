<template>
    <button>
        {{ text }}
    </button>
</template>

<script setup>
defineProps({
    text: {
        type: String,
        default: "Get Started"
    }
})
</script>

<style lang="scss" scoped>
button {
    cursor: pointer;
    background: var(--background-button);
    border: 0px solid var(--background-button);
    color: var(--color-title-light);
    border-radius: 50px;
    padding: .9em 2.2em;
    font-size: 1.4rem;
    font-weight: var(--weight-bold);
    line-height: 1;
}
</style>