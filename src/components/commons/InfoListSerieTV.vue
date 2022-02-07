<template>
  <div class="container-card">
    <!-- poster -->
    <div class="poster">
      <img class="posterCover" :src="(info.poster_path==null)?require('../../assets/img/aaa.jpg'):'https://image.tmdb.org/t/p/w342/'+info.poster_path" alt="">
      <div class="containerList">
        <!-- serie TV list -->
        <ul>
          <li>Title:{{info.name}}</li>
          <li v-if="info.name!=info.original_name">Title original:{{info.original_name}}</li>
          <li class="language-container">
            <img v-if="info.original_language==='en'" src="../../assets/img/en.png">
            <img v-else-if="info.original_language==='es'" src="../../assets/img/es.png">
            <img v-else-if="info.original_language==='it'" src="../../assets/img/it.png">
            <span v-else>{{info.original_language}}</span>  
          </li>
          <li class="vote">
            <span class="starsOuter">
                <span class="starContainer" ><i v-for="(element, index) in getRating(info.vote_average)" :key="index" class="starsInner fas fa-star"></i></span> 
            </span>
          </li>  
        </ul>
      </div>
    </div>
  </div>
</template>

<script>


export default {
  name: 'InfoListSerieTV',
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

<style lang="scss" scoped>
@import "../../assets/style/variabiles.scss";
.container-card{
  display: flex;
  width: calc(100% / 6 - 10px);
  height: 296px;
  margin:10px 5px;
  overflow: hidden;
  .poster{
    position: relative;
    height: 100%;
    .posterCover{
      height: 100%;
    }
    &:hover .containerList{
      display: block;
    }
  .containerList{
    width: 100%;
    height: 100%;
    position: absolute;
    top:0;
    left: 0;
    display: none;
    background-color: rgba(0, 0, 0, 0.411);
      ul{
        padding: 0;
        list-style: none;
        color: $colorWhite;
        li{
          padding: 3px 2px;
        }
        .language-container{
          height: 20px;
          width: 20px;
          img{
            height: 100%;
            object-fit: cover;
          }
        }  
      }
    }
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
