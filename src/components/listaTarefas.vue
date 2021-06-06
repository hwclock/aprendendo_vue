<template>
    <ul>
        <li v-for="tarefa in tarefas"
          :key="tarefa"
          >{{tarefa}}
        </li>
    </ul>
</template>

<script>

export default {
    
    props: {
        tarefas: {
            type: Array, default: () => []
        }
    },
}
</script>