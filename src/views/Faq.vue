<script setup>
import { reactive, ref, onMounted } from 'vue';
import Text from '../components/Text.vue';
const itemArray = reactive([
    {
        title: `What is Frontend Mentor, and how will it help me?`,
        text: `Frontend Mentor offers realistic coding challenges to help developers improve their 
  frontend coding skills with projects in HTML, CSS, and JavaScript. It's suitable for 
  all levels and ideal for portfolio building.`,
    },
    {
        title: `Is Frontend Mentor free?`,
        text: `Yes, Frontend Mentor offers both free and premium coding challenges, with the free 
  option providing access to a range of projects suitable for all skill levels.`,
    },
    {
        title: `Can I use Frontend Mentor projects in my portfolio?`,
        text: `Yes, you can use projects completed on Frontend Mentor in your portfolio. It's an excellent
  way to showcase your skills to potential employers!`,
    },
    {
        title: `How can I get help if I'm stuck on a challenge?`,
        text: `The best place to get help is inside Frontend Mentor's Discord community. There's a help 
  channel where you can ask questions and seek support from other community members.`,
    },
]);

const activeIndex = ref(0);

const handleKeyDown = (event) => {
    switch (event.key) {
        case 'ArrowUp':
            if (activeIndex.value > 0) {
                activeIndex.value--;
            }
            break;
        case 'ArrowDown':
            if (activeIndex.value < itemArray.length - 1) {
                activeIndex.value++;
            }
            break;
    }
};

onMounted(() => {
    document.querySelector('.container').focus();
});
const isEnter = ref(false);
const handleEnter = () => {
    isEnter.value = !isEnter.value;
};
</script>

<template>
    <div
        class="container"
        @keydown="handleKeyDown"
        tabindex="0">
        <div class="h1-wrapper">
            <img
                src="../assets/images/icon-star.svg"
                alt="star-icon"
                class="icon" />
            <h1>FAQs</h1>
        </div>
        <template
            v-for="(item, index) in itemArray"
            :key="index">
            <Text
                :item="item"
                :is-active="index === activeIndex"
                @keydown.enter="handleEnter"
                :is-enter />
            <template v-if="index !== itemArray.length - 1">
                <hr />
            </template>
        </template>
    </div>
</template>

<style scoped>
.container {
    background-color: hsl(0, 0%, 100%);
    margin: 30px;
    position: absolute;
    display: flex;
    align-self: center;
    flex-direction: column;
    border-radius: 10px;
    padding: 30px;
    max-width: 565px;
}
.icon {
    width: 25px;
    height: 25px;
}
.h1-wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
    align-self: flex-start;
}
.h1-wrapper > h1 {
    margin-left: 20px;
}
hr {
    border: 1px solid hsl(275, 100%, 97%);
    margin: 0;
}
.container:focus {
    outline: none;
}
</style>
