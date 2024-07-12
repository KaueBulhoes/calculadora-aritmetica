<template>
  <div class="calculator">
    <div>
      <label for="number1">Número 1:</label>
      <input v-model.number="number1" type="number" id="number1" />
    </div>
    <div>
      <label for="number2">Número 2:</label>
      <input v-model.number="number2" type="number" id="number2" />
    </div>
    <div>
      <label for="operation">Operação:</label>
      <select v-model="operation" id="operation">
        <option value="add">+</option>
        <option value="subtract">-</option>
        <option value="multiply">*</option>
        <option value="divide">/</option>
      </select>
    </div>
    <div>
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: "add",
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "add":
          return this.number1 + this.number2;
        case "subtract":
          return this.number1 - this.number2;
        case "multiply":
          return this.number1 * this.number2;
        case "divide":
          return this.number2 !== 0
            ? this.number1 / this.number2
            : "Erro: Divisão por zero";
        default:
          return 0;
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  display: flex;
  flex-direction: column;
  max-width: 300px;
  margin: 0 auto;
}
.calculator div {
  margin-bottom: 10px;
}
</style>
