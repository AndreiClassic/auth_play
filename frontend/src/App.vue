<script setup>
import { ref, onMounted } from 'vue'

const forecasts = ref([])
const loading = ref(true)

onMounted(async () => {
  try {
    const res = await fetch('http://localhost:8080/weatherforecast')
    forecasts.value = await res.json()
  } finally {
    loading.value = false
  }
})
</script>

<template>
  <div>
    <h1>Weather Forecast</h1>
    <p v-if="loading">Loading...</p>
    <ul v-else>
      <li v-for="item in forecasts" :key="item.date">
        {{ item.date }} - {{ item.temperatureC }}°C ({{ item.summary }})
      </li>
    </ul>
  </div>
</template>

<style scoped>
ul {
  list-style: none;
  padding: 0;
}
li {
  margin: 0.5rem 0;
}
</style>
