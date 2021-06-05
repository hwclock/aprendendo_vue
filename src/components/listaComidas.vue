<template>
    <ul>
        <li v-for="comida in comidas"
          :key="comida"
          >{{comida}}
        </li>
    </ul>
</template>

<script>

export default {
    
    props: {
        comidas: {
            type: Array, default: () => []
        }
    },
    watch: {
        comidas (){
            if (this.comidas.lenght === 5){
                this.$emit('stop', 'Agota ta cheio')
            }
        }
    }
}
</script>