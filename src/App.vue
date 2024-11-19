<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: "add", 
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.num1 + this.num2;
        case "subtract":
          return this.num1 - this.num2;
        case "multiply":
          return this.num1 * this.num2;
        case "divide":
          return this.num2 !== 0 ? this.num1 / this.num2 : "Erro (divisão por zero)";
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="dados">
      <input type="number" v-model.number="num1" placeholder="Digite o primeiro número" />
      <select v-model="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">×</option>
        <option value="divide">÷</option>
      </select>
      <input type="number" v-model.number="num2" placeholder="Digite o segundo número" />
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<style>
body{
  background-color: azure;
  color: #000;
 
}
.calculator {
  max-width: 800px;
  margin: 0;
  text-align: center;
  font-family: Arial, sans-serif;
}

.dados {
  margin: 0 auto;
}

input,
select {
  margin: 0 10px;
  padding: 10px;
  font-size: 16px;
}
option{
  font-weight: bold;
}

.result {
  font-size: 24px;
  font-weight: bold;
}
</style>