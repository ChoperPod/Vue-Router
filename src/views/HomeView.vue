<script setup>
import TheWelcome from '../components/TheWelcome.vue'
import { useCounterStore } from '@/store/counter.js'

const useCounter = useCounterStore();
</script>

<template>
  <!-- <h1>Home counter: {{ useCounter.count }}</h1>
  <h2>Double: {{ useCounter.double }}</h2>
  <button @click="useCounter.increment" class="btn btn-primary">incrementar</button>
  <button @click="useCounter.decrement" class="btn btn-danger">decrementar</button> -->
</template>
