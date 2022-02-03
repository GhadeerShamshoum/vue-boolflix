<template>
  <main>
      <SearchBar 
      @filter="filterMovie"/>
      <InfoMovie
       v-for="(element, index) in  filteredInfo" 
       :key="index"
       :info="element"
       
       />
       <InfoMovie
       v-for="(element, index) in  filteredInfoTv" 
       :key="index"
       :info="element"
       />
    
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
        
          filteredInfo:[],
          filteredInfoTv:[],
          inputText:'*'
      }
  },
  created(){
        this.getInfo();
        this.getInfoTv();
        
  },
  
  methods: {
    filterMovie(inputSearch){
            this.inputText = inputSearch;
            this.getInfo();
            this.getInfoTv();
            
    },
      getInfo: function(){
        axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
            api_key: '5f763b82935ccf722598ab22ec49212e',
            query: this.inputText
        }
      })
      .then((response) => {
        this.filteredInfo = response.data.results;
        console.log( this.filteredInfo, 'movie')
        
      })
      .catch(function (error) {
        console.log(error);
      })
     
      },
      getInfoTv: function(){
        axios.get('https://api.themoviedb.org/3/search/tv', {
        params: {
            api_key: '5f763b82935ccf722598ab22ec49212e',
            query: this.inputText
        }
      })
      .then((response) => {
        this.filteredInfoTV = response.data.results;
        console.log( this.filteredInfoTV, 'tv')
        
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
