<template>
  <div class="cntainerSearchBar">
    <form>
        <input type="text" v-model.trim="inputText" >
        <button @click.prevent="$emit('filter',inputText)">Submit</button>
    </form>
    
  </div>
</template>

<script>


export default {
  name: 'SearchBar',
  data() {
    return {
      inputText: ""
    }
  },
  components: {
     
  },
 
}
</script>

<style lang="scss">
.cntainerSearchBar{
  line-height: 67px;
}

</style>
