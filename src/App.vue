<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from './components/Header.vue'
// import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header
  },
  data() {
      return {
        APIurl: 'https://api.themoviedb.org/3/search/movie?',
        APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT',
        APIquery: '',
      }
    }
}
</script>

<style lang="scss">
@import './style/General';
#app {
  
}
</style>
