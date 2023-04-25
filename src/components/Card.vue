<template>
    <div class="card">
        <div class="ball_card">
            <img src="@/assets/images/icon-brand-recognition.svg" alt="">
        </div>
        <div class="card_description">
            <h3>Brand Recognition</h3>
            <p>Boost your brand recognition with each click. Generic links don’t
                mean a thing. Branded links help instil confidence in your content.</p>
        </div>
    </div>
</template>

<script setup>

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