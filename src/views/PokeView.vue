<script setup>
import axios from 'axios'
const getData = async () => {
    try {
        const { data } = await axios.get(`https://pokeapi.co/api/v2/pokemon/ditto`)
        console.log(data)
    } catch (error) {

    }
};
getData();
</script>

<template>
    <h1>Poke name: {{ $route.params.name }}</h1>
</template>