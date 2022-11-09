<script setup>
import axios from 'axios'
import { ref } from "vue";
import { useRoute, useRouter } from 'vue-router'
const route = useRoute()
const router = useRouter()

const pokem = ref({})

const back = () => {
    router.push("/pokemons")
}

const getData = async () => {
    try {
        const { data } = await axios.get(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`)
        console.log(data);
        pokem.value = data;
    } catch (error) {
        pokem.value = null
    }
};
getData();
</script>

<template>
    <div v-if="pokem">
        <h1>Poke name: {{ $route.params.name }}</h1>
        <img :src="pokem.sprites?.front_default" />
        <img :src="pokem.sprites?.back_default" />
        <img :src="pokem.sprites?.front_shiny" />
        <img :src="pokem.sprites?.back_shiny" />
    </div>
    <h1 v-else>No existe el pokemon</h1>
    <!-- <img :src="pokem.sprites?.front_female"/>
    <img :src="pokem.sprites?.back_female"/>
    <img :src="pokem.sprites?.front_shiny_female"/>
    <img :src="pokem.sprites?.back_shiny_female"/> -->
    <br>
    <button @click="back">Regresar</button>
</template>