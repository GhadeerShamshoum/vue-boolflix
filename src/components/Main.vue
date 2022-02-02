<template>
  <main>
      <SearchBar/>
    
  </main>
</template>

<script>
import axios from "axios";
import SearchBar from "./commons/SearchBar.vue"

export default {
  name: 'Main',
  components: {
      SearchBar 
  },
  methods: {
      getInfo: function(){
        axios.get('https://api.themoviedb.org/3/movie', {
        params: {
            api_key: '5f763b82935ccf722598ab22ec49212e',
            query: 'Potter'
        }
      })
      .then(function (response) {
        console.log(response);
      })
      .catch(function (error) {
        console.log(error);
      })
     
      }

  }
}
</script>

<style lang="scss">

</style>
