<template>
  <div class="m-8">
    <NuxtRouteAnnouncer />
    <div class="flex space-x-6">
      <NuxtLink class="text-2xl font-semibold text-green-600 hover:text-green-800" to="/">Home</NuxtLink>
      <NuxtLink class="text-2xl font-semibold text-green-600 hover:text-green-800" to="/movies">Movies</NuxtLink>
      <NuxtLink class="text-2xl font-semibold text-green-600 hover:text-green-800" to="https://vueschool.io/">Vue School</NuxtLink>      
    </div>
    <NuxtPage />  
  </div>
</template>
