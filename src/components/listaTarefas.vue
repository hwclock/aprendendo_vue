<template>
    <ul>
        <li v-for="tarefa in tarefas" :key="tarefa">
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
        tarefas: Array, default: () => []
    },
    methods: {
        removerTarefa () {
            this.tarefas = []
        }
    }
}
</script>