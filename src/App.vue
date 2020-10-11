<template>
  <div id="app">
  
      <navi/>
    
      <router-view/>
    
  </div>
</template>

<script>

 import Navi from '@/components/Navigation.vue'


export default {
  name: 'App',
  components: {
    Navi
  }
}

</script>

<style lang="scss">

#app {
    width: 100%;
    font-family: 'Hind Siliguri', sans-serif;
}




</style>
