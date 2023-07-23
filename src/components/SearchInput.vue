<script setup lang="ts">
import { ref } from 'vue'

// defineProps<{
//   msg: string
// }>()

const input = ref('')

// fetching data
const handleSubmit = async () => {
  // https://pokeapi.co/api/v2/pokemon/name
}
</script>

<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <input v-model="input" type="text" placeholder="Pokemon" />
      <button type="submit">Search</button>
    </form>
    <p>The Pokemon you're looking for is {{ input }}</p>
  </div>
</template>

<style scoped></style>
