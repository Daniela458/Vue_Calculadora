<template>
  <div>
    <b-container>
    <div class="mt-4">
      <b-row>
      <b-col cols="4">
    <b-form-input v-model="num1" placeholder="numero 1"></b-form-input>
    </b-col>
     <b-col cols="4">
    <div>
    <b-form-select
      v-model="selected"
      :options="options"
      class="mb-3"
      value-field="item"
      text-field="name"
      disabled-field="notEnabled"
    ></b-form-select>
  </div>
    
    </b-col>
    <b-col cols='4'>
    <b-form-input v-model="num2" placeholder="numero 2"></b-form-input>
    </b-col>
    </b-row>
  </div>

    <b-button variant="outline-info" @click="calculo()" class="mt-4">calcular</b-button>
  
  {{resultado}}
  </b-container>
  </div>

</template>

<script>



export default {
  name: 'App',
  data() {
      return {
        num1: 0,
        num2:0,
        selected: '',
        options: [
          { item: 'A', name: '+' },
          { item: 'B', name: '-' },
          { item: 'C', name: '*' },
          { item: 'D', name: '/' }
        ],
        resultado:0
      }},
  components: {
    
  },
  
  methods:{
    calculo: function(){

      switch(this.selected){
        case 'A':
          this.resultado =  parseInt(this.num1) + parseInt(this.num2)
          break
        case 'B':
          this.resultado = this.num1 - this.num2
          break
        case 'C':
          this.resultado = this.num1 * this.num2
          break
        case 'D':
          this.resultado = this.num1 / this.num2
        //console.log(this.resultado)
      }
    }
}
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
