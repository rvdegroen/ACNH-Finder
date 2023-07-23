<script setup lang="ts">
import { ref } from 'vue'

// defineProps<{
//   msg: string
// }>()

const input = ref()

const handler = async () => {}
</script>

<template>
  <div>
    <form @submit.prevent="handler">
      <input v-bind="input" type="text" />
    </form>
  </div>
</template>

<style scoped></style>
