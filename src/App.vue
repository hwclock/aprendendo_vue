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

    <button @click="alterarVisibilidade">
      {{nameButton}}
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
      mostrarLista: false,
      nameButton: "Mostar Lista",
    }
  },
  methods: {
    addTarefa () {
        this.tarefas.push(this.inputTarefa)
        this.inputTarefa = ""
    },
    alterarVisibilidade () {
        this.mostrarLista = !this.mostrarLista
        if(this.mostrarLista){
            this.nameButton = "Esconder Lista"
        }
        else{
            this.nameButton = "Mostar Lista"
        }
    },
  }
}
</script>
