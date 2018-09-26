<template>
  <div id="app" >
    <home-component />
  </div>
</template>

<script>

import HomeComponent from "./components/Home.vue";
export default {
  name: 'app',
  components: {
    'home-component': HomeComponent 
  }
}
</script>

<style lang="css">
    @import '../node_modules/bulma/css/bulma.css';
</style>
