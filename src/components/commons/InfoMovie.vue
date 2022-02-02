<template>
  <ul class="container">
    <li>{{info.title}}</li>
    <li>{{info.original_title}}</li>
    <li>{{info.original_language}}</li>
    <li>{{info.vote_average}}</li>
    
  </ul>
</template>

<script>


export default {
  name: 'InfoMovie',
   props: {
        info: Object
    }
}
</script>

<style lang="scss">
.container{
  height: 300px;
  width: 100%;
  background-color: blue;
}

</style>
