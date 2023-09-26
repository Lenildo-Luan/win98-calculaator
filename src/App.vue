<template>
  <main>
    <section class="section-calculator">
      <Calculator />
    </section>
  </main>
</template>

<script setup>
 import Calculator from './components/section-calculator.vue'
</script>

<style scoped>
  .section-calculator {
    height: 100vh;

    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
