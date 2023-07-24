<script setup lang="ts">
// import TheWelcome from '../components/TheWelcome.vue'
import type { Cocktail } from '@/components/types'
import SearchInput from '../components/SearchInput.vue'
import SearchResults from '../components/SearchResults.vue'
import SearchSummary from '../components/SearchSummary.vue'
import { ref } from 'vue'

// ref<Cocktail[]>() = ref<Cocktail[]>([]), to give it a default value
const cocktailVariable = ref<Cocktail[]>([])

// data that's being passed along, is in the param, with type Cocktail[]
const onUpdateCocktail = (newlyFetchedData: Cocktail[]) => {
  console.log(newlyFetchedData)

  // give value to the data that's being fetched
  cocktailVariable.value = newlyFetchedData
}
</script>

<template>
  <h1>Cocktail Finder</h1>
  <div>
    <!-- listen to emitted event: update-cocktail from SearchInput.vue and run onUpdateCocktail-->
    <SearchInput @update-cocktail="onUpdateCocktail" />
    <!-- show components, when cocktailVariable.length > 0 (fetched data) -->
    <!-- custom attribute that passes dynamic data to use as props in those components-->
    <SearchResults :fetchedCocktails="cocktailVariable" v-if="cocktailVariable.length > 0" />
    <SearchSummary :fetchedCocktails="cocktailVariable" v-if="cocktailVariable.length > 0" />
  </div>
</template>

<style scoped></style>
