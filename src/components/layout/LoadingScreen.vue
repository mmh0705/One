<template>
    <div :class="{ loader: true, fadeout: !isLoading }">
        <img class="logo" src="C:\Users\21500\Desktop\Senior\One\src\components\layout\okat.png" />
    </div>
</template>

<script>
export default {
    name: "LoadingScreen",
    props: ["isLoading"],
};
</script>

<style>
.loader {
    background-color: red;
    bottom: 0;
    color: white;
    display: block;
    font-size: 32px;
    overflow: hidden;
    padding-top: 10vh;
    position: fixed;
    text-align: center;
    top: 0;
    left: 0;
    right: 0;
}

.fadeout {
    animation: fadeout 2s 1s forwards;
}

@keyframes fadeout {
    to {
        opacity: 0;
        visibility: hidden;
    }
}

.logo {
    margin-top: 100px;
}
</style>
