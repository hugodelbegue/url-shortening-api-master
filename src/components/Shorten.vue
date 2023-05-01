<script setup>
import Button from './Button.vue';
import Short from './Short.vue';
</script>

<template>
    <form @submit.prevent="submitForm" class="shorten">
        <div class="input_form">
            <input :class="empty" type="text" placeholder="Shorten a link here..." v-model="input">
            <p v-if="this.error" class="error">Please ass a link</p>
        </div>
        <Button text="Shorten&nbsp;It!" />
    </form>
    <div v-if="this.listLinks != []" :class="space" class="list">
        <Short v-for="link in listLinks" :key="link" :full="link.original" :short="link.short" :copy="link.short" />
    </div>
</template>

<script>
export default {
    mounted() {
        this.getLinkCookie();
    },
    data() {
        return {
            listLinks: [],
            error: false,
            input: ""
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
        submitForm() {
            const input = this.input;
            const url = `https://api.shrtco.de/v2/shorten?url=${input}`;
            const param = {
                method: 'GET'
            }
            this.error = false;
            if (input !== "") {
                fetch(url, param)
                    .then((response) => {
                        if (response.ok) {
                            return response.json();
                        }
                        throw new Error('Request failed!');
                    }, (networkError) => {
                        console.log(networkError.message);
                    }).then((jsonResponse) => {
                        const obj = Object.values(jsonResponse);
                        obj.forEach((link) => {
                            const original = link.original_link
                            const short = link.full_short_link
                            if (original && short) {
                                this.input = "";
                                this.listLinks.push({
                                    original: original,
                                    short: short
                                })
                                if (this.listLinks != []) {
                                    // set a cookie to remember the links
                                    setTimeout(() => {
                                        localStorage.setItem('link', JSON.stringify(this.listLinks));
                                    }, 300);
                                }
                            }
                        })
                    })
                    .catch((error) => {
                        console.log(error);
                    })
            } else {
                this.error = true;
            }
        }
    },
    methods: {
        getLinkCookie() {
            try {
                let cookiesValue = JSON.parse(localStorage.getItem('link'));
                cookiesValue == null ? this.listLinks = [] : this.listLinks = cookiesValue;
            } catch (error) {
                console.log(error);
            }
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
    font-size: var(--font-size-big-button);
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
</style>