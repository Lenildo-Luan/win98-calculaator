<template>
  <div class="calculator-button" :style="{ gridArea: props.area, color: props.color }">
    {{ props.content }}
  </div>
</template>

<script setup>
const props = defineProps({
  content: String,
  area: String,
  color: String
})
</script>

<style scoped>
.calculator-button {
  display: flex;
  justify-content: center;
  align-items: center;

  width: 50px;
  height: 40px;

  background-color: Silver;

  border-top: 2px solid WhiteSmoke;
  border-right: 2px solid black;
  border-bottom: 2px solid black;
  border-left: 2px solid WhiteSmoke;

  font-weight: bold;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
