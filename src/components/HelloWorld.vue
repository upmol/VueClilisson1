<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="display">
      <input v-model.number="operand1" />
      <input v-model.number="operand2" />

      = {{ result }}
    </div>

    <div class="keyboard">
      <button v-on:click="result = operand1 + operand2">+</button>
      <button @click="result = operand1 - operand2">-</button>
      <button @click="division(operand1, operand2)">/</button>
      <button @click="multiply(operand1, operand2)">*</button>
      <button @click="degree(operand1, operand2)">**</button>
      <button @click="trunk(operand1, operand2)">%</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: {
      type: String,
      default: "Empty Props",
    },
  },
  data() {
    return {
      message: "Hello Vue",
      operand1: 0,
      operand2: 0,
      result: 0,
    };
  },
  methods: {
    division(op1, op2) {
      this.result = op1 / op2;
    },
    multiply(op1, op2) {
      this.result = op1 * op2;
    },
    degree(op1, op2) {
      this.result = Math.pow(op1, op2);
    },
    trunk(op1, op2) {
      this.result = op1 % op2;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
