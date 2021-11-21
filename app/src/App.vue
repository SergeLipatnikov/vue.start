<template>
  <div class="form">
    <div class="display">
      <input v-model.number="operand1"/>
      <input v-model.number="operand2"/>
      = {{ result }}
    </div>
    <div class="keyboard">
      <button class="btn" @click="calculate('+')">+</button>
      <button class="btn" @click="calculate('-')">-</button>
      <button class="btn" @click="calculate('/')">/</button>
      <button class="btn" @click="calculate('*')">*</button>
    </div>
    <div class="checkbox">
      <input @change="hidform" type="checkbox" name="cb">
      <label for="cb">Отобразить экранную клавиатуру</label>
      <div v-show="isElVisible" class="num">
      <button @click="input(num)" v-for="num in numbers" :key="num.id" class="btn__num">{{num}}</button>
    </div>
    </div>
    
    <div class="btn__rad">
      <label for="op1">
      <input   type="radio" name="op1">
      Операнд 1</label>
      <label for="op2">
      <input   type="radio" name="op2">
      Операнд 2</label>
    </div>
</div>
  
</template>

<script>
export default {
  name: 'Calculator',
  
  data(){
    return {
      operand1: '',
      operand2: '',
      result: 0,
      isElVisible: false,
      numbers: [1,2,3,4,5,6,7,8,9,0]
    }
    
  },
  methods: {
    calculate (operation = '+') {
      switch (operation) {
        case '+':
          this.add(
            this.result = this.operand1 + this.operand2
          )
          break;
        case '-':
          this.substract(
            this.result = this.operand1 - this.operand2
          )
          break;
        case '*':
          this.multiply(
            this.result = this.operand1 * this.operand2
          )
          break;
        case '/':
          this.divide(
            this.result = this.operand1 / this.operand2
          )
          break;
      }
    },
    hidform() {
      this.isElVisible = !this.isElVisible
    },

  },
}

</script>

<style>
.form {
  display: flex;
  flex-direction: column;
  text-align: center;
}
.display {
  display: flex;
  justify-content: center;
}
.keyboard {
  margin-top: 15px;
  display: flex;
  justify-content: center;
}
.btn {
  color: black;
  background-color: white;
  border: 1px solid black;
  margin-left: 2px;
}
.btn:hover {
  color: white;
  background-color: black;
}
.check__btn {
  margin-top: 10px;
}
.checkbox {
  margin-top: 10px;
}
.btn__num {
  margin: 5px 2px 0 0;
}
.btn__rad {
  margin: 5px 2px 0 0;
}


</style>
