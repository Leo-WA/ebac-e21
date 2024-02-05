<template>
  <div id="app">
    <input v-model.number="number1" type="number" placeholder="Número 1" />
    <input v-model.number="number2" type="number" placeholder="Número 2" />
    <select v-model="operation">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
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
          return this.number2 !== 0 ? this.number1 / this.number2 : 'Divisão por zero';
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
  align-items: center;
  gap: 10px;
}

.calculator input,
.calculator select {
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
}


</style>

