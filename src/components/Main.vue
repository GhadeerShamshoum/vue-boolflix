<template>
  <main>
    <div class="container"> 
      <h1>{{title}}</h1>
      <InfoList
       v-for="(element, index) in  listFilm" 
       :key="index"
       :info="element"
       />
      <InfoList
       v-for="(element, index) in  listSerie" 
       :key="index+'TV'"
       :info="element"
       />
    </div> 
      
    
  </main>
</template>

<script>
import InfoList from "./commons/InfoList.vue";

export default {
  name: 'Main',
  props: {
        listFilm: Array,
        listSerie: Array,
        title: String
    },
  
  components: {

  InfoList
  },
  
}
</script>

<style lang="scss" scoped>
main{
  background-color: #141414;
  display: flex;
  flex-direction: column;
  align-items: center;
  
  h1{
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
