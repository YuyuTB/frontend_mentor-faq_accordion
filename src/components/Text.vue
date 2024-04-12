<script setup>
import { ref, defineProps } from 'vue';
import Buttons from './Buttons.vue';
const isOpen = ref(false);
const props = defineProps({
    item: Object,
    isActive: Boolean,
    isEnter: Boolean,
});
const toggleOpen = () => (isOpen.value = !isOpen.value);
</script>
<template>
    <Buttons
        :is-open
        @isOpen="toggleOpen"
        :title="item.title"
        :class="{ active: isActive }"
        :is-active
        :is-enter />
    <p v-if="isOpen">{{ item.text }}</p>
</template>
<style scoped>
.active {
    border-bottom: 1px solid hsl(292, 42%, 14%);
}
</style>
