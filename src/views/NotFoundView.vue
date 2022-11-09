<script setup>
import { useRouter } from 'vue-router';
const router = useRouter()
const back = () => {
    router.push("/")
}
</script>

<template>
    <h1>Error 404</h1>
    <h4>Page not found</h4>
    <button @click="back">Regresar</button>
</template>