<template>
  <div class="calculator">
    <Display class="calculator-display" :output="equation" />

    <div class="calculator-buttons" >
      <Button
        v-for="button in buttons"
        :key="button.id"
        :content="button.content"
        :area="button.area"
        :color="button.color"
        @click="button.action(button.content)"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
import { evaluate } from 'mathjs'

import Display from './calculator-display.vue'
import Button from './calculator-button.vue'

const equation = ref(' ')
const buttons = reactive([
  { id: 1, content: '1', area: 'one', action: pushContentToEquation, color: 'blue' },
  { id: 2, content: '2', area: 'two', action: pushContentToEquation, color: 'blue' },
  { id: 3, content: '3', area: 'three', action: pushContentToEquation, color: 'blue' },
  { id: 4, content: '4', area: 'four', action: pushContentToEquation, color: 'blue' },
  { id: 5, content: '5', area: 'five', action: pushContentToEquation, color: 'blue' },
  { id: 6, content: '6', area: 'six', action: pushContentToEquation, color: 'blue' },
  { id: 7, content: '7', area: 'seven', action: pushContentToEquation, color: 'blue' },
  { id: 8, content: '8', area: 'eight', action: pushContentToEquation, color: 'blue' },
  { id: 9, content: '9', area: 'nine', action: pushContentToEquation, color: 'blue' },
  { id: 10, content: '0', area: 'zero', action: pushContentToEquation, color: 'blue' },
  { id: 11, content: 'C', area: 'clear', action: cleanEquation, color: 'brow' },
  { id: 12, content: '/', area: 'divide', action: pushContentToEquation, color: 'red' },
  { id: 13, content: '*', area: 'multiply', action: pushContentToEquation, color: 'red' },
  { id: 14, content: '-', area: 'subtract', action: pushContentToEquation, color: 'red' },
  { id: 15, content: '+', area: 'add', action: pushContentToEquation, color: 'red' },
  { id: 16, content: '.', area: 'point', action: pushContentToEquation, color: 'blue' },
  { id: 17, content: '=', area: 'calculate', action: evalEquation, color: 'red' }
])

function pushContentToEquation(content) {
    equation.value = equation.value + content
}

function cleanEquation() {
    equation.value = ' '
}

function evalEquation() {
    equation.value = evaluate(equation.value)
}
</script>

<style scoped>
.calculator {
  padding: 16px;
  background-color: Silver;
  border-top: 2px solid WhiteSmoke;
  border-right: 2px solid black;
  border-bottom: 2px solid black;
  border-left: 2px solid WhiteSmoke;
}

.calculator-display {
    margin-bottom: 8px;
}

.calculator-buttons {
  display: grid;
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  column-gap: 8px;
  row-gap: 8px;
  grid-template-areas:
    'clear . . divide'
    'seven eight nine multiply'
    'four five six subtract'
    'one two three add'
    'zero . point calculate';
}
</style>
