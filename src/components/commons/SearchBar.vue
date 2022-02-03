<template>
  <div>
    <form>
        <input type="text" v-model="inputText" >
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

</style>
