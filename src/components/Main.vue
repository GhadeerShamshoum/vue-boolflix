<template>
  <main>
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

<style lang="scss">

</style>
