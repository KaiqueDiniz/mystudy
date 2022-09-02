<template>
  <q-page>
    <div class="flex flex-center calculator column">
      <h4>Calculadora</h4>
      <div class="column wd-300">
        <q-input v-model="firstNumber" label="Adicione um número"></q-input>
        <q-input v-model="secondNumber" label="Adicione outro número"></q-input>
        <q-btn @click="sum()" label="Somar"></q-btn>
        <q-btn @click="multiply()" label="Multiplicar"></q-btn>
        <q-btn @click="subtract()" label="Subtrair"></q-btn>
        <q-btn @click="divide()" label="Dividir"></q-btn>
      </div>
      <span>O resultado é {{ result }}</span>
    </div>
  </q-page>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const firstNumber = ref('');
    const secondNumber = ref('');
    const result = ref('');

    return {
      firstNumber,
      secondNumber,
      result,
      sum() {
        result.value = Number(firstNumber.value) + Number(secondNumber.value);
      },
      multiply() {
        result.value = Number(firstNumber.value) * Number(secondNumber.value);
      },
      subtract() {
        result.value = Number(firstNumber.value) - Number(secondNumber.value);
      },
      divide() {
        result.value = Number(firstNumber.value) / Number(secondNumber.value);
      },
    };
  },
};
</script>
