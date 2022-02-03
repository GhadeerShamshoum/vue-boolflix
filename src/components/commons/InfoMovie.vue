<template>
  <ul class="container">
    <li>{{info.title}}</li>
    <li>{{info.original_title}}</li>
    <li class="language-container"><img v-if="info.original_language==='en'" src="../../assets/img/en.png">
    <img v-if="info.original_language==='es'" src="../../assets/img/es.png">
    <img v-if="info.original_language==='it'" src="../../assets/img/it.png">
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
  width: 100%;
  .language-container{
    height: 20px;
    width: 20px;
    img{
      height: 100%;
    }
  }
  
}

</style>
