<script setup>
import { reactive } from 'vue';
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
        title: `How can I get help if I'm stuck on a Frontend Mentor challenge?`,
        text: `The best place to get help is inside Frontend Mentor's Discord community. There's a help 
  channel where you can ask questions and seek support from other community members.`,
    },
]);
</script>

<template>
    <div class="container">
        <div class="h1-wrapper">
            <img
                src="../assets/images/icon-star.svg"
                alt="star-icon"
                class="icon" />
            <h1>FAQs</h1>
        </div>
        <Text
            v-for="item in itemArray"
            :key="item.title"
            :item="item" />
    </div>
</template>

<style scoped>
.container {
    background-color: white;
    width: 75%;
    height: 60%;
    position: absolute;
    display: flex;
    align-self: center;
    flex-direction: column;
    border-radius: 10px;
    padding: 30px;
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
</style>
