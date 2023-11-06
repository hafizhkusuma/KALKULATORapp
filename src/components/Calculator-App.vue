<template>
  <div class="calculator">
    <input v-model="display" type="text" id="display" readonly>
    <div class="buttons">
      <button @click="clearDisplay">C</button>
      <button @click="appendToDisplay('7')">7</button>
      <button @click="appendToDisplay('8')">8</button>
      <button @click="appendToDisplay('9')">9</button>
      <button @click="appendToDisplay('+')">+</button>
      <button @click="appendToDisplay('4')">4</button>
      <button @click="appendToDisplay('5')">5</button>
      <button @click="appendToDisplay('6')">6</button>
      <button @click="appendToDisplay('-')">-</button>
      <button @click="appendToDisplay('1')">1</button>
      <button @click="appendToDisplay('2')">2</button>
      <button @click="appendToDisplay('3')">3</button>
      <button @click="appendToDisplay('*')">*</button>
      <button @click="appendToDisplay('0')">0</button>
      <button @click="appendToDisplay('.')">.</button>
      <button @click="calculateResult">=</button>
      <button @click="appendToDisplay('/')">/</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: "",
    };
  },
  methods: {
    appendToDisplay(value) {
      this.display += value;
    },
    clearDisplay() {
      this.display = "";
    },
    calculateResult() {
      try {
        this.display = eval(this.display);
      } catch (error) {
        this.display = "Error";
      }
    },
  },
};
</script>

<style scoped>
.calculator {
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  text-align: center;
  padding: 20px;
}

#display {
  width: 100%;
  height: 40px;
  margin-bottom: 10px;
  font-size: 24px;
}

.buttons button {
  width: 50px;
  height: 50px;
  font-size: 20px;
  margin: 5px;
  cursor: pointer;
}
</style>
