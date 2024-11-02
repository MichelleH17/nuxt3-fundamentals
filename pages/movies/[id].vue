<template>
  <div>
    {{ paramsID }}
  </div>
</template>

<script lang="ts" setup>
const route = useRoute()
const paramsID = route.params.id

</script>

<style>

</style>