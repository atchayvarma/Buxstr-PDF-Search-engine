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


  async asyncData({ $config:{ cx,apiSecret },params }) {
    const query = params.search

    const results = await fetch(
      `https://customsearch.googleapis.com/customsearch/v1?cx=${cx}&safe=active&key=${apiSecret}&hq=filetype:pdf&fileType=pdf&q=${query}`
    ).then(res => res.json())
    return { query, results }
  }
}
</script>

