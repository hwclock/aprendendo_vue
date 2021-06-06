<template>
  <div>
    
    <h1 :style="{color}" > Lista de comidas </h1> 
   
    <input 
      @keyup.enter="addComida"
      v-model="inputComida" 
      type="text">
    
    <button @click="addComida">
      Adicionar Comida
    </button>

    <lista-comidas
      :comidas="comidas"/>

  </div>  

</template>

<script>
import listaComidas from './components/listaComidas.vue'
export default{
  components: { listaComidas },
  data(){
    return{
      inputComida: "",
      color: 'tomato',
      comidas: [],
    }
  },
  methods: {
    addComida () {
      this.comidas.push(this.inputComida)
      this.inputComida = ""
    },
  }
}
</script>

<!--
  DIRETIVAS VUE.JS

  - 
-->