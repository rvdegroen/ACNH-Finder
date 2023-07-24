<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <!-- replaces component with HomeView -->
  <header>
    <nav>
      <RouterLink to="/">Cocktail Finder</RouterLink>
      <RouterLink to="/todolist">Todo List</RouterLink>
    </nav>
  </header>
  <main>
    <RouterView />
  </main>
</template>

<style scoped></style>
