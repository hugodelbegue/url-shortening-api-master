<script setup>
import Logo from '@/components/Logo.vue';
</script>

<template>
    <footer>
        <div class="layout_footer body_size">
            <Logo color="#fff" />
            <div class="layout_links">
                <div class="links_footer">
                    <div class="group_links">
                        <h3>Features</h3>
                        <ul>
                            <li>Link Shortening</li>
                            <li>Branded Links</li>
                            <li>Analytics</li>
                        </ul>
                    </div>
                    <div class="group_links">
                        <h3>Resources</h3>
                        <ul>
                            <li>Blog</li>
                            <li>Developers</li>
                            <li>Support</li>
                        </ul>
                    </div>
                    <div class="group_links">
                        <h3>Company</h3>
                        <ul>
                            <li>About</li>
                            <li>Our Team</li>
                            <li>Careers</li>
                            <li>Contact</li>
                        </ul>
                    </div>
                </div>
                <div class="social_footer">
                    <ul>
                        <span class="social_icon">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="var(--color-title-light)"
                                viewBox="0 0 448 512"><!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M400 32H48A48 48 0 0 0 0 80v352a48 48 0 0 0 48 48h137.25V327.69h-63V256h63v-54.64c0-62.15 37-96.48 93.67-96.48 27.14 0 55.52 4.84 55.52 4.84v61h-31.27c-30.81 0-40.42 19.12-40.42 38.73V256h68.78l-11 71.69h-57.78V480H400a48 48 0 0 0 48-48V80a48 48 0 0 0-48-48z" />
                            </svg>
                        </span>
                        <span class="social_icon">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="var(--color-title-light)"
                                viewBox="0 0 512 512"><!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z" />
                            </svg>
                        </span>
                        <span class="social_icon">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="var(--color-title-light)"
                                viewBox="0 0 496 512"><!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M496 256c0 137-111 248-248 248-25.6 0-50.2-3.9-73.4-11.1 10.1-16.5 25.2-43.5 30.8-65 3-11.6 15.4-59 15.4-59 8.1 15.4 31.7 28.5 56.8 28.5 74.8 0 128.7-68.8 128.7-154.3 0-81.9-66.9-143.2-152.9-143.2-107 0-163.9 71.8-163.9 150.1 0 36.4 19.4 81.7 50.3 96.1 4.7 2.2 7.2 1.2 8.3-3.3.8-3.4 5-20.3 6.9-28.1.6-2.5.3-4.7-1.7-7.1-10.1-12.5-18.3-35.3-18.3-56.6 0-54.7 41.4-107.6 112-107.6 60.9 0 103.6 41.5 103.6 100.9 0 67.1-33.9 113.6-78 113.6-24.3 0-42.6-20.1-36.7-44.8 7-29.5 20.5-61.3 20.5-82.6 0-19-10.2-34.9-31.4-34.9-24.9 0-44.9 25.7-44.9 60.2 0 22 7.4 36.8 7.4 36.8s-24.5 103.8-29 123.2c-5 21.4-3 51.6-.9 71.2C65.4 450.9 0 361.1 0 256 0 119 111 8 248 8s248 111 248 248z" />
                            </svg>
                        </span>
                        <span class="social_icon">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="var(--color-title-light)"
                                viewBox="0 0 448 512"><!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z" />
                            </svg>
                        </span>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/responsive.scss';

footer {
    --space-container-links: 3em;
    --space-link: 3em;
    --size-shortly: 2.3rem;
    --endpoint-top: calc(var(--endpoint) + 1rem);

    @media #{$tabletScreen} {
        --space-container-links: 6em;
    }
}

h2,
h3 {
    color: var(--color-title-light);
}

h2 {
    font-size: var(--size-shortly);
}

h3 {
    font-size: var(--font-size);
    margin-bottom: 1.1em;
}

.layout_footer {
    text-align: center;
    background: var(--background-footer);
    padding-top: var(--endpoint-top);
    padding-bottom: var(--endpoint);

    @media #{$desktopScreen} {
        display: flex;
        place-content: space-between;
    }
}

.layout_links {
    @media #{$desktopScreen} {
        display: flex;
        gap: var(--space-container-links);
    }
}

.links_footer {
    display: flex;
    flex-direction: column;
    gap: var(--space-container-links);
    margin-top: var(--space-link);
    margin-bottom: var(--space-link);

    @media #{$tabletScreen} {
        place-content: center;
        flex-direction: row;
    }

    @media #{$desktopScreen} {
        margin-top: 0;
    }

    .group_links {
        @media #{$tabletScreen} {
            text-align: left;
        }
    }

    ul {
        display: flex;
        flex-direction: column;
        gap: .6em;
    }
}

.social_footer {
    ul {
        display: flex;
        place-content: center;
        gap: 1.3em;
    }
}

.social_icon {
    svg {
        cursor: pointer;
        width: 29px;
        transition: .25s ease;

        &:hover {
            fill: var(--background-button);
        }

        &:active {
            fill: var(--background-button);
        }
    }
}
</style>