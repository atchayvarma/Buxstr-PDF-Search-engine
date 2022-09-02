<template>

  <div class="w-1/2 bg-gray2 rounded-full inline-flex justify-between">

    <input placeholder="Search" v-model="searchTerm"  v-on:keyup.enter="onEnter"  class="bg-transparent w-10/12 my-3 ml-10 outline-none text-white font-bold font-montserrat font-bold placeholder-" >

    <NuxtLink accesskey="e" :to="`${searchTerm}`" class=" bg-primary p-3 m-2 rounded-full justify-self-end " >
      <svg width="30" height="30" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M32.6333 30.9098L27.4772 25.8687L27.3564 25.685C27.1317 25.4612 26.8244 25.3352 26.5038 25.3352C26.1831 25.3352 25.8758 25.4612 25.6511 25.685C21.2692 29.705 14.5172 29.9235 9.87301 26.1956C5.22879 22.4676 4.1335 15.9501 7.31353 10.9653C10.4936 5.98046 16.9621 4.07527 22.4293 6.5132C27.8964 8.95114 30.6657 14.9757 28.9005 20.5914C28.7734 20.9971 28.8773 21.4383 29.1731 21.7487C29.4689 22.0592 29.9116 22.1918 30.3346 22.0966C30.7575 22.0014 31.0963 21.6929 31.2235 21.2872C33.3336 14.623 30.1466 7.45133 23.7242 4.41159C17.3017 1.37184 9.57126 3.37624 5.53358 9.12813C1.49591 14.88 2.36277 22.6532 7.5734 27.4193C12.784 32.1853 20.7747 32.5138 26.3762 28.1923L30.9415 32.6558C31.413 33.1147 32.1752 33.1147 32.6467 32.6558C33.1178 32.1903 33.1178 31.4409 32.6467 30.9754L32.6333 30.9098Z" fill="white"/>
      </svg>
    </NuxtLink>

  </div >
</template>

<script>
export default {
  name: "SearchBar",
  props:{
    "searchQuery": String,
  },
  data() {
    return {
      searchTerm: this.searchQuery
    }
  },
  methods: {

      onEnter:function (){
      }

  }

}
</script>

<style scoped>

</style>
