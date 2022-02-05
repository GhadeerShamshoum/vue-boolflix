<template>
  <header>
      <SearchBar 
      @filter="PassChoice"/>
      
  </header>
</template>

<script>

import SearchBar from "./commons/SearchBar.vue";


export default {
  name: 'Header',
  
  components: {
  SearchBar 
  },
  methods:{

    PassChoice(value) {
        this.$emit('passTOApp',value);
    }
  } 
}
</script>

<style lang="scss">

</style>
