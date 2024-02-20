<template>
  <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <input v-model.number="num1" type="number" class="input-field" />
    <select v-model="operator" class="input-field">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model.number="num2" type="number" class="input-field" />
    <p class="result">{{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
    };
  },
  computed: {
    result() {
      switch (this.operator) {
        case '+':
          return this.num1 + this.num2;
        case '-':
          return this.num1 - this.num2;
        case '*':
          return this.num1 * this.num2;
        case '/':
          return this.num1 / this.num2;
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
  margin-top: 50px;
}

.input-field {
  margin: 10px;
  padding: 5px;
  font-size: 18px;
}

.result {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>