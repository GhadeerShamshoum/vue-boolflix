<template>
    <nav>
        <ul class="menu">
            <li v-for="(element, index) in links" :key="index">
                <a :class='{active: element.current==true}' href="#">{{element.text}}</a>
            </li>
        </ul>
        
    </nav>
 
</template>

<script>


export default {
  name: 'Menu',
  data(){
      return{
          links:[
              {
                text:"Home",
                url:"#",
                current:true
              },
              {
                text:"Serie TV",
                url:"#",
                current:false
              },
              {
                text:"Film",
                url:"#",
                current:false
              },
              {
                text:"Original",
                url:"#",
                current:false
              },
              {
                text:"Aggiunti di recente",
                url:"#",
                current:false
              },
              {
                text:"La mia lista",
                url:"#",
                current:false
              }
              
          ]
      }
  }
  
}

</script>

<style lang="scss" >
.menu{
    list-style: none;
    display: flex;
    margin: 0 50px;
    a{
        color: white;
        padding: 0 10px;
        font-weight: 200;
        &:hover{
            font-weight: 500;
        }
    }
}

.active{
    font-weight: 500 !important;
}

</style>
