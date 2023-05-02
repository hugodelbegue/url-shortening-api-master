<template>
    <article class="card">
        <div class="ball_card">
            <img :src="img" :alt="alt(title)">
        </div>
        <div class="card_description">
            <h3>{{ title }}</h3>
            <p>{{ text }}</p>
        </div>
    </article>
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
            alt(title) {
                return "Icon de la la section " + title;
            }
        }
    }
}
</script>

<style lang="scss" scoped>
article {
    --width-ball: 95px;
}

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
    width: 100%;
}

.ball_card {
    background: var(--background-tersiary);
    display: flex;
    place-content: center;
    place-items: center;
    border-radius: 50%;
    width: var(--width-ball);
    height: auto;
    aspect-ratio: 1 / 1;

    position: absolute;
    top: calc(var(--width-ball) / -2);

    img {
        height: 50%;
    }
}

.card_description {
    display: flex;
    flex-direction: column;
    gap: var(--space-title-text);
}
</style>