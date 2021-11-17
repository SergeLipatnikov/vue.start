<template>
  <div class="form">
    <div class="display">
      <input v-model="operand1"/>
      <input v-model="operand2"/>
      = {{result || '0'}}
    </div>
    <div class="keyboard">
      <button class="btn" v-on:click="result = operand1 + operand2">+</button>
      <button class="btn" v-on:click="result = operand1 - operand2">-</button>
      <button class="btn" @click="result = operand1 / operand2">/</button>
      <button class="btn" @click="result = operand1 * operand2">*</button>
    </div>
      <div></div>
    <div>

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
      result: '',
    }
  },
  methods: {

  }
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
</style>
