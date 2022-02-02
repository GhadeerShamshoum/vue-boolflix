<template>
  <main>
      <SearchBar 
      @filter="filterMovie"/>
      <InfoMovie
       v-for="(element, index) in  filteredInfo" 
       :key="index"
       :info="element"/>
    
  </main>
</template>

<script>
import axios from "axios";
import SearchBar from "./commons/SearchBar.vue";
import InfoMovie from "./commons/InfoMovie.vue";

export default {
  name: 'Main',
  
  components: {
  SearchBar,
  InfoMovie 
  },

  data(){
      return{
        apiURL:"https://api.themoviedb.org/3/search/movie",
          filteredInfo:[],
          inputText:''
      }
  },
  created(){
        this.getInfo();
        
  },
  
  methods: {
    filterMovie(inputSearch){
            this.inputText = inputSearch;
            this.getInfo();
            
    },
      getInfo: function(){
        axios.get(this.apiURL, {
        params: {
            api_key: '5f763b82935ccf722598ab22ec49212e',
            query: 'Harry'
        }
      })
      .then((response) => {
        this.filteredInfo = response.data.results;
        console.log( this.filteredInfo)
        
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
