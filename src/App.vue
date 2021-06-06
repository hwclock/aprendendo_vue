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

    <button @click="() => this.mostrarLista = !this.mostrarLista">
      {{mostrarLista ? "Esconder Lista" : "Mostrar lista"}}
    </button>

    <lista-tarefas
      :tarefas="tarefas"
      :mostrarLista="mostrarLista"/>
  
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
      mostrarLista: true,
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
