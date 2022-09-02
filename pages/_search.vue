<template>
<div class="flex flex-col bg-gray1">

  <div class="flex flex-row ">
    <NuxtLink class="w-1/12 ml-5" to="/">
    <BuxstrlLogo/>
    </NuxtLink>

    <SearchBar class="m-3 " :searchQuery="query"/>
  </div>
<div class="flex flex-col m-10">
  <ResultCard class="mb-10" v-for="result in results.items" :title="result.title" :link="result.link" :snippet="result.snippet" />
</div>




</div>
</template>

<script>
export default {
  name: "_search",

  data(){
    return{
      results:[],
    }
  },
  async fetch(){
    this.results = await fetch(
      `https://customsearch.googleapis.com/customsearch/v1?cx=f5283cd8111bc4a85&safe=active&key=AIzaSyBUuT-Epnmmne1tt1PcFwEVkE2rid7-LNQ&hq=filetype:pdf&fileType=pdf&q=${this.query}`
    ).then(res => res.json())
  },
  async asyncData({ params }) {
    const query = params.search // When calling /abc the slug will be "abc"
    return { query }
  }
}
</script>

<style scoped>

</style>
