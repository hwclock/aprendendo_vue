<template>
    <ul v-if="mostrarLista">
        <li v-for="(tarefa, index) in tarefas" :key="`${tarefa}-${index}`">
            {{tarefa}}
            <button
                @click="removerTarefa">
                Remover
            </button>
        </li>
    </ul>
</template>

<script>
export default {
    props: {
        tarefas: Array, default: () => [],
        mostrarLista: Boolean
    },
    methods: {
        removerTarefa () {
            this.tarefas = []
        }
    }
}
</script>