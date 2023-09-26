<template>
  <div class="calculator-button" :style="{ gridArea: props.area }">
    {{ props.content }}
  </div>
</template>

<script setup>
const props = defineProps({
  content: String,
  area: String
})
</script>

<style scoped>
.calculator-button {
  display: flex;
  justify-content: center;
  align-items: center;

  width: 50px;
  height: 50px;

  background-color: #b9b9b9;
  box-shadow: rgba(119, 117, 116, 0.5) 0px 0px 5px, rgba(119, 117, 116, 0.4) -1px 1px 5px,
    rgba(119, 117, 116, 0.3) -2px 2px 5px, rgba(119, 117, 116, 0.2) -3px 3px 5px,
    rgba(119, 117, 116, 0.1) -4px 4px 5px, rgba(119, 117, 116, 0.09) -5px 5px 5px,
    rgba(119, 117, 116, 0.08) -6px 6px 5px, rgba(119, 117, 116, 0.07) -7px 7px 5px,
    rgba(119, 117, 116, 0.06) -8px 8px 5px, rgba(119, 117, 116, 0.05) -9px 9px 5px,
    rgba(119, 117, 116, 0.04) -10px 10px 5px;

  border-top: 2px solid #bebebe;
  border-right: 2px solid #ffffff;
  border-bottom: 2px solid #b5b4b5;
  border-left: 2px solid #868484;
}
</style>
