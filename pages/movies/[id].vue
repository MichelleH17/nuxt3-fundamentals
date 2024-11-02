<template>
  <div>
    <pre>{{ data }}</pre>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute()

const { data } = await useAsyncData(() => {
  return $fetch(`http://www.omdbapi.com/?apikey=4203574e&i=${route.params.id}`)
})
</script>