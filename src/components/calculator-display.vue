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
  height: 40px;
  padding: 0 8px;
  background-color: white;
  display: flex;
  justify-content: right;
  align-items: center;

  border-top: 2px solid black;
  border-right: 2px solid LightGrey;
  border-bottom: 2px solid LightGrey;
  border-left: 2px solid black;
  
  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
