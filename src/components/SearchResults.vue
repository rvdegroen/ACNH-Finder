<script setup lang="ts">
import type { Cocktail } from './types'

defineProps<{
  // prop from parent container with fetched cocktails as Cocktail type
  fetchedCocktails: Cocktail[]
}>()
</script>

<template>
  <h2>{{ fetchedCocktails.length }} cocktails found</h2>
  <!-- for every cocktail in fetchedCocktails (with type Cocktail[]) -->
  <div v-for="(cocktail, index) in fetchedCocktails" :key="index">
    <h3>{{ cocktail.name }}</h3>
    <h4>Instructions</h4>
    <p class="white">{{ cocktail.instructions }}</p>
    <!-- <p>Ingredients: {{ cocktail.ingredients.join(', ') }}</p> -->
    <h4>Ingredients</h4>
    <ul v-for="(ingredient, index) in cocktail.ingredients" :key="index">
      <li>{{ ingredient }}</li>
    </ul>
  </div>
</template>

<style scoped>
div {
  max-width: 40em;
  margin: 20px auto;
  background-color: rgb(39, 39, 39);
  padding: 10px 30px;
  border-radius: 10px;
}

h2 {
  color: rgb(255, 122, 144);
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

h3 {
  color: rgb(255, 122, 144);
}

h4 {
  color: rgb(253, 172, 186);
}

ul {
  list-style: none;
}

.white {
  color: white;
}

p {
  text-align: left;
}
</style>
