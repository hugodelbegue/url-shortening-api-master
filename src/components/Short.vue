<script setup>
import Button from './Button.vue';
</script>

<template>
    <div class="shorten_link" :class="style">
        <div class="full_link">{{ full }}</div>
        <hr>
        <div class="short_interaction">
            <div class="short_link">{{ short }}</div>
            <Button :text="button" />
        </div>
    </div>
</template>

<script>
export default {
    props: {
        full: {
            type: String
        },
        short: {
            type: String
        },
        button: {
            type: String
        },
        style: {
            type: Object
        }
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/responsive.scss';

.shorten_link {
    --color-url: var(--very-dark-blue);
    --color-url-short: var(--background-button);
    background: var(--background-primary);
    border-radius: calc(var(--angles-block) + 5px);
    text-align: left;
    width: -webkit-fill-available;
    margin-top: 1.8rem;

    @media #{$tabletScreen} {
        display: flex;
        place-items: center;
        place-content: space-between;
    }

    hr {
        width: 100%;

        @media #{$tabletScreen} {
            display: none;
        }
    }

    button {
        width: 100%;
        border-radius: var(--angles-block);
        font-size: var(--size-font-shorten);

        @media #{$tabletScreen} {
            padding: .6em 1.8em;
        }
    }
}

.full_link {
    color: var(--color-url);
}

.short_link {
    color: var(--color-url-short);
}

.short_interaction {
    display: flex;
    flex-direction: column;
    gap: var(--side);

    @media #{$tabletScreen} {
        flex-direction: row;
        place-items: center;
    }
}

.full_link,
.short_link {
    line-height: 1;
}

.full_link,
.short_interaction {
    padding: var(--side);

    @media #{$tabletScreen} {
        --side: 1.2rem 1.6rem;
    }
}
</style>