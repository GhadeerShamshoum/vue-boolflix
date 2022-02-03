<template>
  <ul class="container">
    <li class="poster">
      <img class="posterCover" :src="'https://image.tmdb.org/t/p/w500/'+info.poster_path" alt="">
    </li>
    <li>{{info.title}}</li>
    <li>{{info.original_title}}</li>
    <li>{{info.name}}</li>
    <li>{{info.original_name}}</li>
    <li class="language-container">
      <img v-if="info.original_language==='en'" src="../../assets/img/en.png">
      <img v-else-if="info.original_language==='es'" src="../../assets/img/es.png">
      <img v-else-if="info.original_language==='it'" src="../../assets/img/it.png">
      <span v-else>{{info.original_language}}</span>
      
    </li>
    <li>{{info.vote_average}}</li>
    
  </ul>
</template>

<script>


export default {
  name: 'InfoMovie',
   props: {
        info: Object
    },
    methods: {
      
    }
}
</script>

<style lang="scss">
.container{
  height: 300px;
  width: 200px;
  .language-container{
    height: 20px;
    width: 20px;
    img{
      height: 100%;
      object-fit: cover;
    }
  }  
}
ul{
  list-style: none;
}
.poster{
  
  height: 200px;
  .posterCover{
    height: 100%;
  }
}

</style>
