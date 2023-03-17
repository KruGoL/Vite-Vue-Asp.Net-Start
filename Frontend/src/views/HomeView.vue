<script setup lang="ts">
import { ref } from 'vue'
import TheWelcome from '../components/TheWelcome.vue'
import axios from 'axios'

const weather = ref([])

const tags = async () => {
  const resp = await axios.get('/WeatherForecast')
  weather.value = resp.data
  console.log(weather)
}

tags()
</script>

<template>
  <main>
    <h1>{{ weather[1].summary }}</h1>
    <TheWelcome />
  </main>
</template>
