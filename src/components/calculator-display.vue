<template>
  <div class="calculator-display">
    {{ props.output }}
  </div>
</template>

<script setup>
const props = defineProps({
  output: Number
})
</script>

<style scoped>
.calculator-display {
  height: 50px;
  padding: 10px;
  background-color: white;
  display: flex;
  justify-content: right;
  align-items: center;

  border-top: 2px solid #b5b4b5;
  border-right: 2px solid #868484;
  border-bottom: 2px solid #bebebe;
  border-left: 2px solid #ffffff;
}
</style>
