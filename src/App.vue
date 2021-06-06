<template>
  <div>
   
    <h1 :style="{color}" >Lista Tarefas </h1>

    <input
      type="text"
      v-model="inputTarefa"
      @keyup.enter="addTarefa">

    <button @click="addTarefa">
      Adicionar
    </button>
  
  </div>  

</template>

<script>
export default{
  data(){
    return{
      inputTarefa: "",
      color: 'tomato',
      tarefas: [],
    }
  },
  methods: {
    addTarefa () {
      this.tarefas.push(this.inputTarefa)
      this.inputTarefa = ""
    },
  }
}
</script>

<!--
  DIRETIVAS VUE.JS

  - 
-->