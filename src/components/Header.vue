<template>
  <header>
    <div class="headerLeft">
      <Logo/>
      <Menu/>
    </div>
    <SearchBar 
    @filter="PassChoice"/>
      
  </header>
</template>

<script>

import SearchBar from "./commons/SearchBar.vue";
import Menu from "./commons/Menu.vue";
import Logo from "./commons/Logo.vue";


export default {
  name: 'Header',
  
  components: {
  Logo, 
  Menu,
  SearchBar
  },
  methods:{

    PassChoice(value) {
        this.$emit('passTOApp',value);
    }
  } 
}
</script>

<style lang="scss">
header{
  height: 67px;
  padding: 0 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #010606;
  .headerLeft{
    display: flex;
    align-items: center;
  }
}

</style>
