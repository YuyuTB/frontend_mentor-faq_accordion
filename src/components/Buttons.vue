<script setup>
import { ref, defineProps, defineEmits, onMounted } from 'vue';
const props = defineProps({
    isOpen: Boolean,
    title: String,
    isActive: Boolean,
});
const isOpen = ref(props.isOpen);
const emit = defineEmits(['isOpen']);

const toggleOpen = () => {
    isOpen.value = !isOpen.value;
    console.log(props.isActive);
    emit('isOpen');
};
</script>
<template>
    <div
        class="line"
        @click="toggleOpen">
        <h2 :class="{ open: isOpen }">{{ props.title }}</h2>
        <img
            :src="
                isOpen
                    ? '../public/images/icon-minus.svg'
                    : '../public/images/icon-plus.svg'
            "
            :alt="isOpen ? 'minus icon' : 'plus icon'"
            class="icon" />
    </div>
</template>
<style scoped>
.line {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
h2:hover {
    color: #8d45b3;
}
.line:hover {
    cursor: pointer;
}
.open {
    color: #8d45b3;
}
</style>
