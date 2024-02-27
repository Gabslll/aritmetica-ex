<script setup>
  import { reactive, ref } from 'vue';

  const calculadora = reactive({
    numero1: null,
    numero2: null,
    operacao: 'soma',
  });

  const done = ref(null);

  const calcularResultado = () => {
    const num1 = parseFloat(calculadora.numero1);
    const num2 = parseFloat(calculadora.numero2);
    
    switch (calculadora.operacao) {
      case 'soma':
        return num1 + num2;
      case 'subtracao':
        return num1 - num2;
      case 'multiplicacao':
        return num1 * num2;
      case 'divisao':
        return num1 / num2;
      default:
          return null;
    }
  }

  const atualizarResultado = () => {
    done.value = calcularResultado();
  }
;
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
    <h1>Operação Aritmética</h1>
    <form @input="atualizarResultado">
      <div class="row">
        <div class="col-md-2 mt-4">
          <input v-model="calculadora.numero1" type="number" class="form-control mb-2" placeholder="Insira um número aqui">
          <input v-model="calculadora.numero2" type="number" class="form-control" placeholder="Insira um número aqui">
        </div>
        <div class="col-md-2 mt-4">
          <select v-model="calculadora.operacao" class="form-control">
            <option value="soma">Soma</option>
            <option value="subtracao">Subtração</option>
            <option value="multiplicacao">Multiplicação</option>
            <option value="divisao">Divisão</option>
          </select>
          <h2 class="mt-2 ms-2">O resultado é {{ done }}</h2>
        </div>
      </div>
    </form>
  </header>
</template>

  <style scoped>
  .done {
    text-decoration: line-through;
  }
  </style>
