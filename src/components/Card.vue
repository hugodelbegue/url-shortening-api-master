<template>
    <div class="card">
        <div class="ball_card">
            <img :src="imgUrl(img)" :alt="alt(title)">
        </div>
        <div class="card_description">
            <h3>{{ title }}</h3>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script setup>
defineProps({
    img: {
        type: String
    },
    title: {
        type: String
    },
    text: {
        type: String
    },
})
</script>
<script>
export default {
    data() {
        return {
            imgUrl(file) {
                return new URL(`../assets/images/${file}`, import.meta.url).href;
            },
            alt(title) {
                return "Icon de la la section " + title;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
h3 {
    font-size: 1.25em;
}

.card {
    position: relative;
    background: var(--background-primary);
    display: flex;
    place-content: center;
    padding-top: 4.3em;
    padding-bottom: 2.4em;
    padding-left: 1.6em;
    padding-right: 1.6em;
    border-radius: 7px;
}

.ball_card {
    background: var(--background-tersiary);
    display: flex;
    border-radius: 50%;
    width: fit-content;
    padding: 1.7rem;

    position: absolute;
    top: -45px;
}

.card_description {
    display: flex;
    flex-direction: column;
    gap: var(--space-title-text);
}
</style>