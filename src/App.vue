<script setup>
  import { reactive } from 'vue';
  import Title from './components/Title.vue'
  import Math from './components/Math.vue'
  import Res from './components/Res.vue'

  const calculadora = reactive({
    operation: '+',
    numero1: '',
    numero2: ''
  })

  const resultado = () => {
    const {operation} = calculadora
    switch (operation) {
      case '-':
        return parseFloat(calculadora.numero1) - parseFloat(calculadora.numero2)
      case '*':
        return parseFloat(calculadora.numero1) * parseFloat(calculadora.numero2)
      case '/':
        return parseFloat(calculadora.numero1) / parseFloat(calculadora.numero2)
      default: 
        return parseFloat(calculadora.numero1) + parseFloat(calculadora.numero2)
    }
  }
</script>

<template>
  <body>
    <div class="container">
      <Title></Title>
      <Math :operacao="evento => calculadora.operation = evento.target.value" :numero1="evento => calculadora.numero1 = evento.target.value" :numero2="evento => calculadora.numero2 = evento.target.value"></Math>
      <Res :numero1="calculadora.numero1" :numero2="calculadora.numero2" :result="resultado()" ></Res>
    </div>
  </body>
</template>

