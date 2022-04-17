<template>
  <div class="hello">
    <div class="display">
      <input v-model.number="operand1" />
      <input v-model.number="operand2" />
      = {{ result }}
    </div>
    <div class="keyboard">
      <button @click="sum">+</button>
      <button @click="result = operand1 - operand2">-</button>
      <button @click="sub">/</button>
      <button @click="result = operand1 * operand2">*</button>
      <button @click="degree">a^b</button>
      <button @click="integ">Деление без остатка</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      operand1: 0,
      operand2: 0,
      result: 0,
    };
  },
  methods: {
    sum() {
      this.result = this.operand1 + this.operand2;
    },
    sub() {
      this.result = this.operand1 / this.operand2;
    },
    degree() {
      this.result = Math.pow(this.operand1, this.operand2);
    },
    integ() {
      this.result = Math.floor(this.operand1 / this.operand2);
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
