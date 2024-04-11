<script setup>
import Faq from './views/Faq.vue';
import Attribution from './components/Attribution.vue';
</script>

<template>
    <div class="purple-background">
        <img
            src="./assets/images/background-pattern-mobile.svg"
            alt="background-purple"
            class="background-purple" />

        <Faq />
        <Attribution class="attribution" />
    </div>
</template>

<style scoped>
.background-purple {
    align-self: flex-start;
    width: 100%;
}
.purple-background {
    width: 100%;
    height: 100svh;
    background-color: #f4e9fa;
    display: flex;
    justify-content: center;
    position: fixed;
}
.attribution {
    position: fixed;
    bottom: 0;
    width: 100%;
}
</style>
