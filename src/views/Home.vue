<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <input v-model.number="operand1" type="number"/>
    <input v-model.number="operand2" type="number"/>
    
    <p>={{result}},{{text}}</p>
    <br/>
    <button v-on:click="plus(operand1,operand2)">+</button>
    <button v-on:click="minus(operand1,operand2)">-</button>
    <button @click="multiplication(operand1,operand2)">*</button>
    <button @click="division(operand1,operand2)">/</button>

     
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  },
  data(){
    return{
      operand1:0,
      operand2:0,
      result:0,
      text: ' ',
       visible: true
    }
  },
  methods:{
    plus(op1,op2){
      this.result = op1+op2;
      this.text ='done'
    },
    minus(op1,op2){
      this.result = op1 - op2;
      this.text ='done'
    },
    multiplication(op1,op2){
      this.result = op1 * op2;
      this.text ='done'
    },
    division(op1,op2){
      if (op2>0){
        this.result= Math.floor(op1 / op2) //целочисленное деление
        this.text ='done'
      } else{
        this.text= 'операция невозможна'
      }
    }

  }
}
</script>
