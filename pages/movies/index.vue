<script setup lang="ts">
const query = ref("")

function search() {
  $fetch(`http://www.omdbapi.com/?apikey=4203574e&s=${query.value}`)
}
</script>

<template>
  <form @submit.prevent="search">
    <input type="text" v-model="query">
    <button>Search</button>
  </form>
</template>

<style scoped></style>