<script setup lang="ts">
import { ref } from 'vue'
import type { Cocktail } from './types'

// defineProps<{
//   msg: string
// }>()

const query = ref('')

// fetching data
const handleSubmit = async () => {
  // https://pokeapi.co/api/v2/pokemon/name
  const response = await fetch(`https://api.api-ninjas.com/v1/cocktail?name=${query.value}`, {
    headers: {
      // src: https://stackoverflow.com/questions/71083110/vue-uncaught-referenceerror-process-is-not-defined/71406233#71406233
      'X-Api-Key': import.meta.env.VITE_API_KEY
    }
  })
  const cocktails: Cocktail[] = await response.json()
  console.log(cocktails)

  query.value = ''
}
</script>

<template>
  <div>
    <p v-if="query">The Pokemon you're looking for is {{ query }}</p>
    <form @submit.prevent="handleSubmit">
      <input v-model="query" type="text" placeholder="Pokemon" />
      <button type="submit">Search</button>
    </form>
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
</style>
