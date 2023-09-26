<template>
  <div class="calculator">
    <Display class="calculator-display" :output="equation" />

    <div class="calculator-buttons" >
      <Button
        v-for="button in buttons"
        :key="button.id"
        :content="button.content"
        :area="button.area"
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
  { id: 1, content: '1', area: 'one', action: pushContentToEquation  },
  { id: 2, content: '2', area: 'two', action: pushContentToEquation },
  { id: 3, content: '3', area: 'three', action: pushContentToEquation },
  { id: 4, content: '4', area: 'four', action: pushContentToEquation },
  { id: 5, content: '5', area: 'five', action: pushContentToEquation },
  { id: 6, content: '6', area: 'six', action: pushContentToEquation },
  { id: 7, content: '7', area: 'seven', action: pushContentToEquation },
  { id: 8, content: '8', area: 'eight', action: pushContentToEquation },
  { id: 9, content: '9', area: 'nine', action: pushContentToEquation },
  { id: 10, content: '0', area: 'zero', action: pushContentToEquation },
  { id: 11, content: 'C', area: 'clear', action: cleanEquation},
  { id: 12, content: '/', area: 'divide', action: pushContentToEquation },
  { id: 13, content: '*', area: 'multiply', action: pushContentToEquation },
  { id: 14, content: '-', area: 'subtract', action: pushContentToEquation },
  { id: 15, content: '+', area: 'add', action: pushContentToEquation },
  { id: 16, content: '.', area: 'point', action: pushContentToEquation },
  { id: 17, content: '=', area: 'calculate', action: evalEquation }
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
  padding: 10px;
  background-color: #b9b9b9;
  border-top: 2px solid #bebebe;
  border-right: 2px solid #ffffff;
  border-bottom: 2px solid #b5b4b5;
  border-left: 2px solid #868484;
}

.calculator-display {
    margin-bottom: 10px;
}

.calculator-buttons {
  display: grid;
  grid-template-columns: 50px 50px 50px 50px;
  grid-template-rows: auto;
  column-gap: 10px;
  row-gap: 10px;
  grid-template-areas:
    'clear . . divide'
    'seven eight nine multiply'
    'four five six subtract'
    'one two three add'
    'zero . point calculate';
}
</style>
