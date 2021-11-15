<template>
  <div>
     <div class="display">
       <input v-model="operand1"/>
       <input v-model="operand2"/>
       = {{result}}
     </div>
     <div class="keyboard">
   <button v-on:click="result = operand1 + operand2">+</button>
   <button v-on:click="result = operand1 - operand2">-</button>
   <button @click="result = operand1 / operand2">/</button>
   <button @click="result = operand1 * operand2">*</button>
 </div>
  </div>


</template>

<script>
export default {
   name: 'Calculator',
   data(){
       return {
           operand1: 0,
           operand2: 0,
           result: 0
       }
   }
 }

</script>

<style>
.display {
  display: flex;
}
.keyboard {
  margin-top: 15px;
}
</style>
