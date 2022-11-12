<script setup>
import { useRoute, useRouter } from 'vue-router'
import { useGetData } from '@/composables/getData'

const route = useRoute()
const router = useRouter()

const back = () => {
    router.push("/pokemons")
}

const { data, error, loading, getData } = useGetData();
getData(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`);
</script>

<template>
    <p v-if="loading">Cargando...</p>
    <h1 class="alert alert-danger mt-2" v-if="error"> {{ error }}<br>No existe el pokemon!!!</h1>
    <button @click="back" class="btn btn-outline-primary" v-if="error">Regresar</button>
    <div v-else>
        <div v-if="data">
            <h1>Poke name: {{ $route.params.name }}</h1>
            <img :src="data.sprites.front_default" alt="" />
            <img :src="data.sprites.back_default" alt="" />
            <img :src="data.sprites.front_shiny" alt="" />
            <img :src="data.sprites.back_shiny" alt="" />
            <br>
            <button @click="back" class="btn btn-outline-primary">Regresar</button>
        </div>
    </div>
</template>