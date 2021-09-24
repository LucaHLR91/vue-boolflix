<template>
  <div id="app">
    
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    data() {
      return {
        APIurl: 'https://api.themoviedb.org/3/search/movie?',
        APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT',
        APIquery: '',
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  
}
</style>
