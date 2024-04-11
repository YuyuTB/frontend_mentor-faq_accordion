<script setup>
  import Faq from "./components/Faq.vue";
</script>

<template>
    <div class="purple-background">
      <div class="faq-background-image">
        <Faq />
      </div>
    </div>
</template>

<style scoped>
  .faq-background-image{
    background-image: url('./assets/images/background-pattern-mobile.svg');
    width: 100%;
    height: 230px;
  }
  .purple-background{
    width: 100%;
    height: 100svh;
    background-color: #F4E9FA;
  }
</style>
