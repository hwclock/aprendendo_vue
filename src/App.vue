<template>
  <div>
    
    <!--<h1 :style="{color}" > Hello {{inputComida}} </h1> -->
    <h1 :style="{color}"> Lista de Comidas</h1>
   
    <input 
      @keyup.enter="adicionarComida"
      v-model="inputComida" 
      type="text">
    
    <button @click="adicionarComida">
      Adicionar Comida
    </button>

    <lista-comidas 
      @stop="handleStoper"
      :comidas="comidas"/>

  </div>

</template>

<script>
import listaComidas from './components/listaComidas'
export default{
  components: {listaComidas},
  data(){
    return{
      inputComida: "",
      color: 'tomato',
      comidas: [],
    }
  },
  methods: {
    adicionarComida () {
      this.comidas.push(this.inputComida)
      this.inputComida = ""
    },
    handleStoper (payload){
        window.alert(payload)
    }
  }
}
</script>
