<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',

  data() {
    return {
      inputStr: '',
      result: ''
    }
  },

  methods: {
    updateDisplay(val) {
      this.inputStr = this.inputStr + val
    },
    calculate () {
      this.result = eval(this.inputStr)
      this.inputStr = this.result
    },
    clearDisplay () {
      this.inputStr = ''
    }
  }
}
</script>

<template>
  <body>
    <div class="container">
      <div class="display">
        <form action="" @submit.prevent="calculate" >
          <input type="text" class="display" v-model="inputStr">
        </form>
      </div>

      <div class="buttons">

        <div class="row">
          <div class="col-auto">
            <button @click="() => updateDisplay('+')" class="btn btn-ops">+</button>
            <button @click="() => updateDisplay('-')" class="btn btn-ops">-</button>
            <button @click="() => updateDisplay('*')" class="btn btn-ops">x</button>
            <button @click="() => updateDisplay('/')" class="btn btn-ops">÷</button>
          </div>
        </div>

        <div class="row">
          <div class="col-auto">
            <button @click="() => updateDisplay('7')" class="btn btn-number">7</button>
            <button @click="() => updateDisplay('8')" class="btn btn-number">8</button>
            <button @click="() => updateDisplay('9')" class="btn btn-number">9</button>
            <button @click="() => updateDisplay('.')" class="btn btn-number">.</button>
          </div>
        </div>

        <div class="row">
          <div class="col-auto">
            <button @click="() => updateDisplay('4')" class="btn btn-number">4</button>
            <button @click="() => updateDisplay('5')" class="btn btn-number">5</button>
            <button @click="() => updateDisplay('6')" class="btn btn-number">6</button>
            <button @click="() => clearDisplay()" class="btn btn-number">AC</button>
          </div>
        </div>

        <div class="row">
          <div class="col-auto">
            <button @click="() => updateDisplay('1')" class="btn btn-number">1</button>
            <button @click="() => updateDisplay('2')" class="btn btn-number">2</button>
            <button @click="() => updateDisplay('3')" class="btn btn-number">3</button>
            <button @click="() => calculate()" class="btn btn-number">=</button>
          </div>
        </div>

        <div class="row">
          <div class="col-auto">
            <button @click="() => updateDisplay('0')" class="btn btn-number">0</button>  
          </div>
        </div>
        
      </div>
    </div>
  </body>
</template>

<style scoped>

.btn {
  margin: 4px;
  width: 44px;
  height: 44px;
}
.container {
  width: 100%;
  margin: auto;
  position: relative;
  left: 10%;
}
.btn-ops {
  background-color: #6C5F5B;
  color: #F6F1EE;
}
.btn-number {
  background-color: #4F4A45;
  color: #F6F1EE;
}
.btn-bottom {
  background-color: #F6F1EE;
}
.display {
  height: 42px;
  border-radius: 8px;
  margin-bottom: 20px;
  margin-top: 8px;
}
.buttons {
  margin-bottom: 8px;
}
.container {
  background-color: #ED7D31;
  border-radius: 8px;
}
</style>
