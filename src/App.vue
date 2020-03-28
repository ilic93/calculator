<template>
  <div class="calculator">
    <div class="result">0</div>
    <div class="btn">AC</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">/</div>
    <div class="btn">7</div>
    <div class="btn">8</div>
    <div class="btn">9</div>
    <div class="btn operator">*</div>
    <div class="btn">4</div>
    <div class="btn">5</div>
    <div class="btn">6</div>
    <div class="btn operator">-</div>
    <div class="btn">1</div>
    <div class="btn">2</div>
    <div class="btn">3</div>
    <div class="btn operator">+</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>

export default {
  name: 'App'
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

.operator {
  background-color: orange;
}

.zero {
  grid-column: 1 / 3;
}

</style>
