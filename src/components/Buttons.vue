<script setup>
import { ref, defineProps, defineEmits } from 'vue';
const props = defineProps({ isOpen: Boolean, title: String });
const isOpen = ref(props.isOpen);
const emit = defineEmits(['isOpen']);

const toggleOpen = () => {
    isOpen.value = !isOpen.value;
    emit('isOpen');
};
</script>
<template>
    <div class="line">
        <h2 @click="toggleOpen">{{ props.title }}</h2>
        <img
            :src="
                isOpen
                    ? '/src/assets/images/icon-minus.svg'
                    : '/src/assets/images/icon-plus.svg'
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
</style>
