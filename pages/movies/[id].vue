<template>
  <div>
    <pre>{{ data }}</pre>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute()
// shortshand for $fetch within useAsyncData
const { data } = await useFetch(`http://www.omdbapi.com/?apikey=4203574e&i=${route.params.id}`, {
  pick: ["Plot", "Title", "Error"],
  key: `/movies/${route.params.id}`,
})

if (data.value.Error === "Incorrect IMDb ID.") {
      showError({ statusCode: 404, statusMessage: "Page not found" })
    }  
/* const { data } = await useAsyncData(`/movies/${route.params.id}`, () => {
  return $fetch(`http://www.omdbapi.com/?apikey=4203574e&i=${route.params.id}`)
},
{
  pick: ["Plot", "Title"],
  // pick je upřednostněný před transform
  /*transform(data) {
    return {
      Plot: data.Plot,
      Title: data.Title,
    }
  },
}) */
</script>