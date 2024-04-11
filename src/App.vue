<script setup>
import Faq from './views/Faq.vue';
import Attribution from './components/Attribution.vue';
import { ref, onMounted, onBeforeUnmount } from 'vue';

const breakpoint = 1440;
const imageSource = ref('');

const updateImageSource = () => {
    if (window.innerWidth >= breakpoint) {
        imageSource.value = '/src/assets/images/background-pattern-desktop.svg';
    } else {
        imageSource.value = '/src/assets/images/background-pattern-mobile.svg';
    }
};

updateImageSource();

const resizeHandler = () => {
    updateImageSource();
};

onMounted(() => {
    window.addEventListener('resize', resizeHandler);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize', resizeHandler);
});
</script>

<template>
    <div class="purple-background">
        <img
            :src="imageSource"
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
    background-color: hsl(275, 100%, 97%);
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
