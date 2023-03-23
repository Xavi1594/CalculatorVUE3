<script>
import { ref } from 'vue';
export default {
  name: "App",
  setup() {
    let screen = ref(0);
    function concatNum(num){
      screen.value === 0 ? (screen.value = num ) : (screen.value += num)
    }
    function concatOp(op){
if (screen.value === 0 || screen.value === "," ){
  if (op == ',') { 
    screen.value = op 
    return
  } else { 
    return
  }
}
screen.value += op
    }
    function clear () {
      screen.value = 0 
    }
    function evaluate() {
      screen.value = eval(screen.value)
    }
    return {evaluate, clear, concatNum, concatOp, screen}
  }
}


</script>

<template>
  <div id="calculator">
    <div class="screen">{{ screen }}</div>
    <div @click="clear()" class="btn clear">C</div>
    <div class="btn conversor">$</div>

    <div @click="concatNum('7')" class="btn number">7</div>
    <div @click="concatNum('8')" class="btn number">8</div>
    <div @click="concatNum('9')" class="btn number">9</div>
    <div @click="concatNum('4')" class="btn number">4</div>
    <div @click="concatNum('5')" class="btn number">5</div>
    <div @click="concatNum('6')" class="btn number">6</div>
    <div @click="concatNum('1')" class="btn number">1</div>
    <div @click="concatNum('2')" class="btn number">2</div>
    <div @click="concatNum('3')" class="btn number">3</div>
    <div @click="concatNum('0')" class="btn number">0</div>
    
    <div @click="concatOp('*')" class="btn">*</div>
    <div @click="concatOp ('+')"  class="btn">+</div>
    <div @click="concatOp ('-')" class="btn">-</div>
    <div @click="concatOp ('/')" class="btn">/</div>
    <div @click="evaluate() ('=')" class="btn">=</div>
    <!-- <div @click="concatOp (',')" class="btn">,</div> -->
    <!-- <div @click="concatOp ('%')" class="btn">%</div>
    <div @click="concatOp ('√')" class="btn">√</div> -->











    



  </div>
</template>

<style scoped>

#calculator {
  border: 2px solid black;
  width: 400px;
  margin: 0 auto;
  border-radius: 5px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  background-color:#D9D9D9;
}
.screen {
  width: 100%;
  background-color: #17A600;
  color: black ;
  text-align: right;
  font-size: 30px;
  padding: 15px;
}
.btn {
  width: 26%;
  text-align: center ;
  color: black;
  background-color: #D9D9D9;
  border-radius: 4%;
  cursor: pointer;
  margin: 5px;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  padding-top: 5px;
  padding-bottom: 5px;
  border: 2px solid black;
}
.btn:hover {
  opacity: 0.5 ;
}
.btn.number {
  width: 26%;
  text-align: center ;
  color: black;
  background-color: palevioletred;
  border-radius: 4%;
  cursor: pointer;
  margin: 5px;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  padding-top: 5px;
  padding-bottom: 5px;
  border: 2px solid black;
}
.btn.clear {
  background-color: orange;
  width: 40%;
  border-radius: 10%;
}
.btn.conversor{
  background-color: yellow;
  width: 40%;
  border-radius: 10%;
}
</style>

