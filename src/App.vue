<template>
  <div>
    
    <!--<h1 :style="{color}" > Hello {{inputComida}} </h1> -->
    <h1 :style="{color}"> Tarefas</h1>
   
    <input 
      @keyup.enter="addTarefa"
      v-model="inputTarefa" 
      type="text">
    
    <button @click="addTarerfa">
      Adicionar Tarefa
    </button>

    <lista-tarefas 
      :tarefas="tarefas"/>

  </div>  

</template>

<script>
import listaTarefas from './components/listaTarefas'
export default{
  components: {listaTarefas},
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