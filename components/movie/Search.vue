<script setup>
const query = ref("")
const movies = ref([])

async function search() {
  const { Search } = await $fetch(`http://www.omdbapi.com/?apikey=4203574e&s=${query.value}`)
  movies.value = Search
}
</script>

<template>
  <div>
    <form @submit.prevent="search" class="flex space-x-2 my-4">
      <input type="text" v-model="query" class="border-2 border-gray-300 p-2 shadow-md rounded-lg w-96">
      <button class="border-2 border-green-400 p-2 shadow-md rounded-lg bg-green-500 hover:bg-green-600 text-white text-xl font-medium">Search</button>
    </form>
    <ul class="flex flex-wrap space-x-3 list-none">
      <li v-for="movie in movies" :key="movie.imdbID">
        <NuxtLink :to="{ name: 'movies-id', params: { id: movie.imdbID } }">
          <img :src="movie.Poster" :alt="movie.title" width="200"/>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>