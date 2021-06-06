<template>
    <ul>
        <li v-for="comida in comidas" :key="comida">
            {{comida}}
        </li>
    </ul>
</template>

<script>
export default {
    props: {
        comidas: Array, default: () => []
    }
}
</script>