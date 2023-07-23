<script setup lang="ts">
// import TheWelcome from '../components/TheWelcome.vue'
import SearchInput from '../components/SearchInput.vue'
import SearchResults from '../components/SearchResults.vue'
import SearchSummary from '../components/SearchSummary.vue'
</script>

<template>
  <h1>Pokemon Finder</h1>
  <div>
    <SearchInput />
    <SearchResults />
    <SearchSummary />
  </div>
</template>

<style scoped></style>
