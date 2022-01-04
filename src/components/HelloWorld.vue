<script setup>
import { ref } from 'vue'

let responseMessage = ref(null)

const getTestData = async () => {
  const response = await fetch('http://localhost:3000/test.json')
  const json = await response.json()
  responseMessage.value = json.message
}

getTestData()
</script>

<template>
  <h1>Docketwise Client Test</h1>

  <p>{{ responseMessage }}</p>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
