<template>
  <div>
    <pre>{{ data }}</pre>
  </div>
</template>

<script lang="ts" setup>
const route = useRoute()
// shortshand for $fetch within useAsyncData
const { data } = useFetch(`http://www.omdbapi.com/?apikey=4203574e&i=${route.params.id}`, {
  pick: ["Plot", "Title"],
  key: `/movies/${route.params.id}`,
})
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