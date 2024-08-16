<script setup>
import { reactive } from 'vue';

let operacao = reactive({
  num1: 0,
  num2: 0,
  operation: 'nenhum',
})

const calcular = () => {
  switch (operacao.operation) {
    case "somar":
      return operacao.num1 + operacao.num2;
    case "subtrair":
      return operacao.num1 - operacao.num2;
    case "multiplicar":
      return operacao.num1 * operacao.num2;
    case "dividir":
      return operacao.num1 / operacao.num2;
  }
}

</script>

<template>
  <div class="container">
    <input type="number" name="" v-model.number="operacao.num1" id="numero1">
    <input type="number" name="" v-model.number="operacao.num2" id="numero2">

    <select name="" id="" @change="evento => operacao.operation = evento.target.value">
      <option value="nenhum">Nenhum</option>
      <option value="somar">Somar</option>
      <option value="subtrair">Subtrair</option>
      <option value="multiplicar">Multiplicar</option>
      <option value="dividir">Dividir</option>
    </select>

    <h1>
      {{ calcular()}}
    </h1>
  </div>

</template>

<style scoped>
  .container {
    max-width: 600px;
    margin: 150px auto;
    align-items: center;
  }

  input, select{
    display: inline-block;
    margin: 0 10px;
    padding: 5px;
    border-radius: 5px;
  }

  h1 {
    display: block;
    text-align: center;
  }

  select {
    align-items: center;
  }

</style>
