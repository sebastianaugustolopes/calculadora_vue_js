<script setup>
import Form from './components/Form.vue';
import { reactive } from 'vue';

const estado = reactive({
  number1: 0,
  number2: 0,
  Answer: 0,
  operation: 'sum'
})

function getnumber1(evento){
  estado.number1 = evento.target.value;
  if(estado.number1 === ''){
    estado.number1 = 0;
  }
  estado.number1 = parseFloat(estado.number1);
  getCalculation();
}

function getnumber2(evento){
  estado.number2 = evento.target.value;
  if(estado.number2 === ''){
    estado.number2 = 0;
  }
  estado.number2 = parseFloat(estado.number2);
  getCalculation();
}

function getOperation(evento){
  estado.operation = evento.target.value;
  getCalculation();
}

function getCalculation(){
  switch(estado.operation){
    case 'sum':
      estado.Answer = estado.number1 + estado.number2;
      break;
    case 'subtract':
      estado.Answer = estado.number1 - estado.number2;
      break;
    case 'multiply':
      estado.Answer = estado.number1 * estado.number2;
      break;
    case 'divide':
      estado.Answer = estado.number1 / estado.number2;
      break;
  }
}

</script>

<template>
  <div class="container">
    <Form 
    :getnumber1="getnumber1"
    :getnumber2="getnumber2"
    :getOperation="getOperation"
    :Answer="estado.Answer"
    />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
}

body {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: black;
}
</style>