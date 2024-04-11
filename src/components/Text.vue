<script setup>
import { ref, defineProps } from 'vue';
import Buttons from './Buttons.vue';
const isOpen = ref(false);
const props = defineProps({ item: Object });

const toggleOpen = () => (isOpen.value = !isOpen.value);
</script>
<template>
    <Buttons
        :is-open="isOpen"
        @isOpen="toggleOpen"
        :title="item.title" />
    <p v-if="isOpen">{{ item.text }}</p>
</template>
<style scoped></style>
