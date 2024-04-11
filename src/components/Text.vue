<script setup>
import { ref, defineProps } from 'vue';
import Buttons from './Buttons.vue';
const isOpen = ref(false);
const props = defineProps({ item: Object });
const items = ref(props.item);
</script>
<template>
    <div class="line">
        <h2>{{ item.title }}</h2>
        <Buttons :is-open="isOpen" />
    </div>
    <p>{{ item.text }}</p>
</template>
<style scoped>
.line {
    display: grid;
    grid-template-columns: 4fr 1fr;
    gap: 10px;
}
</style>
