<script setup>
import Button from './Button.vue';
</script>

<template>
    <div class="shorten_link">
        <div class="full_link">{{ full }}</div>
        <hr>
        <div class="short_interaction">
            <div class="short_link">{{ short }}</div>
            <Button @click="copyPress(copy)" :class="{ copied: text == 'Copied!' }" :text="text" />
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
        copy: {
            type: String
        }
    },
    data() {
        return {
            text: "Copy"
        }
    },
    methods: {
        // copy link
        copyPress(copy) {
            if (copy) {
                this.text = "Copied!"
                navigator.clipboard.writeText(copy)
            } else {
                console.log('error copy');
            }
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

    @media #{$tabletScreen} {
        display: flex;
        place-items: center;
        place-content: space-between;
    }

    hr {
        width: 100%;
        border-color: var(--background-secondary);

        @media #{$tabletScreen} {
            display: none;
        }
    }

    button {
        width: 100%;
        border-radius: var(--angles-block);
        font-size: var(--font-size-small-button);

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

// Class

.copied {
    --color-copied: var(--very-dark-blue);
    background-color: var(--color-copied);
    border-color: var(--color-copied);
    pointer-events: none;
}
</style>