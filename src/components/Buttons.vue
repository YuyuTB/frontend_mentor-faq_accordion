<script setup>
import { ref, defineProps } from 'vue';
const props = defineProps({ isOpen: Boolean });
const isOpen = ref(props.isOpen);
</script>
<template>
    <img
        src="../assets/images/icon-minus.svg"
        alt="minus icon"
        class="icon"
        v-if="isOpen"
        @click="isOpen = !isOpen" />
    <img
        src="../assets/images/icon-plus.svg"
        alt="plus icon"
        class="icon"
        v-else
        @click="isOpen = !isOpen" />
</template>
<style scoped></style>
