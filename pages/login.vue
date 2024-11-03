<template>
  <form>
    <h1>Login</h1>
    <label>
      Username
      <input type="text" class="border-2 border-gray-300 p-2 shadow-md rounded-lg w-96" />
    </label>
    <label>
      Password
      <input type="password" class="border-2 border-gray-300 p-2 shadow-md rounded-lg w-96" />
    </label>
  </form>
</template>

<script setup>
definePageMeta({
  layout: 'plain',
})
</script>