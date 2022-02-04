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
    <li class="vote">
      <span class="starsOuter">
        <span >
          <span class="starContainer" ><i v-for="(element, index) in getRating(info.vote_average)" :key="index" class="starsInner fas fa-star"></i></span> 
        </span>
      </span>
    </li>
    
  </ul>
</template>

<script>


export default {
  name: 'InfoMovie',
  data(){
    return{
      
    }
  },
   props: {
        info: Object
    },
    methods: {
      getRating(ratings){
       const numberDivision = ratings / 2;
       const numberRounded = Math.round(numberDivision);
       console.log(numberRounded)
       return numberRounded
       
      },    
      
    }
}
</script>

<style lang="scss">

.container{
  height: 300px;
  width: 500px;
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
.starsOuter{
  position: relative;
  display:inline-block;
}
.starsInner{
  color: rgb(247, 224, 22);
}
.starsOuter::before{
  content: "\f005 \f005 \f005 \f005 \f005";
  font-family: 'Font Awesome 5 Free';
  font-weight: 900;
  color: rgb(199, 196, 196);
  
}
.starContainer{
  position: absolute;
   display:inline-block;
  top:0;
  left: 0;
}


</style>
