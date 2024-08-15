<script setup>
  
</script>

<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input type="number" v-model.number="number1" placeholder="Primeiro número">
      
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
      
      <input type="number" v-model.number="number2" placeholder="Segundo número">
      
      <div class="result">
        Resultado: <span>{{ result }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: null,
      number2: null,
      operation: null,
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case 'add':
          return this.number1 + this.number2;
        case 'subtract':
          return this.number1 - this.number2;
        case 'multiply':
          return this.number1 * this.number2;
        case 'divide':
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Erro: Impossível dividir por 0';
        default:
          return 0;
      }
    }
  }
};
</script>

<style scoped>
  #app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}

.calculator {
  display: inline-block;
  text-align: left;
}

input {
  margin: 5px;
  padding: 10px;
  font-size: 18px;
  width: 200px;
}

select {
  margin: 5px;
  padding: 10px;
  font-size: 18px;
}

.result {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>
