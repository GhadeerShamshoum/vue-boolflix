<template>
  <main>
    <div class="container"> 
      <h2>{{title}}</h2>
      <InfoListMovies
       v-for="(element, index) in  listFilm" 
       :key="index"
       :info="element"
       />
      <InfoListSerieTV
       v-for="(element, index) in  listSerie" 
       :key="index+'TV'"
       :info="element"
       />
    </div> 
      
    
  </main>
</template>

<script>
import InfoListMovies from "./commons/InfoListMovies.vue";
import InfoListSerieTV from "./commons/InfoListSerieTV.vue";

export default {
  name: 'Main',
  props: {
        listFilm: Array,
        listSerie: Array,
        title: String
    },
  
  components: {

  InfoListMovies,
  InfoListSerieTV
  },
  
}
</script>

<style lang="scss" scoped>
main{
  background-color: #141414;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 60px 0;
  
  h2{
    color: white;
    width: 100%;

  }
  .container{
    width: 1200px;
    display: flex;
    flex-wrap: wrap;
  }
}

</style>
