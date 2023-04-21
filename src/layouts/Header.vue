<template>
    <header>
        <div class="layout_header size_body">
            <h2>Shortly</h2>
            <nav class="burger_menu">
                <input type="checkbox" id="burger">
                <label for="burger">
                    <div class="icon_menu"></div>
                </label>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    setup() {


        return {}
    }
}
</script>

<style lang="scss" scoped>
input[type="checkbox"] {
    display: none;
}

label {
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    width: var(--size-burger);
    height: auto;
    aspect-ratio: 1/1;
}

.layout_header {
    display: flex;
    place-content: space-between;
    place-items: center;
    padding-top: var(--endpoint-padding);
}


.icon_menu,
.icon_menu::before,
.icon_menu::after {
    content: "";
    position: relative;
    display: flex;
    background: var(--color-text);
    width: 100%;
    height: 4px;
}

.icon_menu::before {
    position: absolute;
    top: 12px;
}

.icon_menu::after {
    position: absolute;
    bottom: 12px;
}
</style>