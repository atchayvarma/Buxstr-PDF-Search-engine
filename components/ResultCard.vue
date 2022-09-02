<template>

  <div>
    <a :href="link" class="text-white text-3xl w-1/2 font-montserrat font-bold hover:underline">{{title}}</a>
    <h1 class="text-primary text-lg mt-2 w-1/2 font-montserrat font-bold">{{link}}</h1>
    <h1 class="text-white opacity-50 w-1/2 mt-2 font-montserrat font-bold">{{snippet}}</h1>
  </div>

</template>

<script>
export default {
  name: "ResultCard",
  props:{
    "title":String,
    "link":String,
    "snippet":String
  }
}
</script>

<style scoped>

</style>
