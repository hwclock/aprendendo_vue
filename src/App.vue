<template>
  <div>
    
    <h1 :style="{color}" > Lista de Tarefas </h1> 
   
    <input 
      @keyup.enter="addTarefa"
      v-model="inputTarefa" 
      type="text">
    
    <button @click="addTarefa">
      Adicionar Tarefa
    </button>

    <lista-tarefas
      :tarefas="tarefas"/>
  
  </div>  

</template>

<script>
import ListaTarefas from './components/listaTarefas.vue'
export default{
  components: { ListaTarefas },
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