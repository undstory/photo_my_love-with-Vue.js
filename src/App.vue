<template>
  <div id="app">
  
      <navi/>
    
      <router-view/>
    
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

 import Navi from '@/components/Navigation.vue'


export default {
  name: 'App',
  components: {
    Navi
  },
  
  

}

</script>

<style lang="scss">

@import "./styles/variables.scss";
@import "./styles/mixins.scss";

#app {
    width: 100%;
    font-family: 'Hind Siliguri', sans-serif;
    color: $font-color;
}




</style>
