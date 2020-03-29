<template>
  <div class="calculator">
    <div class="result">{{ this.result || 0 }}</div>
    <div class="btn" @click="clear">AC</div>
    <div class="btn" @click="prefix">+/-</div>
    <div class="btn" @click="percent">%</div>
    <div class="btn operator">/</div>
    <div class="btn" @click="addNumber(7)">7</div>
    <div class="btn" @click="addNumber(8)">8</div>
    <div class="btn" @click="addNumber(9)">9</div>
    <div class="btn operator">*</div>
    <div class="btn" @click="addNumber(4)">4</div>
    <div class="btn" @click="addNumber(5)">5</div>
    <div class="btn" @click="addNumber(6)">6</div>
    <div class="btn operator">-</div>
    <div class="btn" @click="addNumber(1)">1</div>
    <div class="btn" @click="addNumber(2)">2</div>
    <div class="btn" @click="addNumber(3)">3</div>
    <div class="btn operator">+</div>
    <div class="btn zero" @click="addNumber(0)">0</div>
    <div class="btn" @click="dot">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      result: ''
    }
  },
  methods: {
    addNumber(num) {
      if(this.result.length >= 20) return
      if(this.result == '0' && num == '0') return
      this.result = `${this.result}${num}`
    },
    clear() {
      this.result = ''
    },
    prefix() {
      this.result = this.result.charAt(0) === '-' ? this.result.replace('-', '') : `-${this.result}`
    },
    percent() {
      this.result = `${parseFloat(this.result) / 100}`
    },
    dot() {
      this.result = !this.result.includes('.') ? `${this.result}.` : this.result
    }
  }
}
</script>

<style>

body {
  background-image: url('https://storage.needpix.com/rsynced_images/matrix-1461373324WTC.jpg');  
}

.calculator {
  width: 500px;
  border: 2px solid black;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 50px;
  text-align: center;
  font-size: 35px;
}

.result {
  background-color: lightblue;
  grid-column: 1 / 5;
}

.btn {
  background-color: grey;
  border: 1px solid black;
}

.btn:hover {
  cursor: pointer;
  background-color: lightgrey;
}

.operator {
  background-color: orange;
}

.zero {
  grid-column: 1 / 3;
}

</style>
