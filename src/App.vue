<template>
  <div id="app">
    <Header @passTOApp="filterData"/>
    <Main :listFilm="filteredInfoFilm" :listSerie="filteredInfoTv" 
    title="Your search results"/>
    
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  data(){
      return{
        
          filteredInfoFilm:[],
          filteredInfoTv:[],
          inputText:'*'
      }
  },
  components: {
    Header,
    Main
  },
  computed: {

    // arrayFilm(){
    //   const arrayObjMod = [];
    //   this. filteredInfoFilm.forEach((elem) => {
    //     const objApp = {
    //       title: elem.title,
    //       title_original: elem.original_title,
    //       language: elem.original_language,
    //       voto: elem.vote_average
    //     };
    //     arrayObjMod.push(objApp);
    //   });
    //   return arrayObjMod;
    // },
    // arraySerie(){
    //   const arrayObjMod = [];
    //   this.filteredInfoTv.forEach((elem) => {
    //     const objApp = {
    //       title: elem.name,
    //       name_original: elem.original_name,
    //       language: elem.original_language,
    //       voto: elem.vote_average
    //     };
    //     arrayObjMod.push(objApp);
    //   });
    //   return arrayObjMod;
    // },
    // arrayFilmsSerie() {
    //     return [...this.arrayFilm, ...this.arraySerie];
    // }
  },

  methods: {
    filterData(inputSearch){
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
        this.filteredInfoFilm = response.data.results;
        console.log( this.filteredInfoFilm, 'movie')
        
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
        this.filteredInfoTv = response.data.results;
        console.log( this.filteredInfoTv, 'tv')
        
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
