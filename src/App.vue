<template>
  <div id="app">
    <Header  @searchContent="startSearch" />
    <ContentView :ContentList= 'ContentList' />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import ContentView from './components/ContentView.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    Header,
    ContentView
  },
  data() {
    return {
      contentToSearch: '',
      ContentList: [],
      APIurlMovies: 'https://api.themoviedb.org/3/search/movie?',
      APIurlTvSeries: 'https://api.themoviedb.org/3/search/tv?',
      APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT&query=',
    }
    
  },
  methods: {
    startSearch(contentToSearch) {
      this.contentToSearch = contentToSearch;
      this.getMovies();
      this.getTvSeries();
      console.log(contentToSearch)
    },
    getMovies() {
      axios.get(this.APIurlMovies + this.APIkey + this.contentToSearch)
      .then(res => {
        console.log(res.data.results);
        this.ContentList= res.data.results;
        console.log(this.ContentList)
      })
    },
    getTvSeries() {
      axios.get(this.APIurlTvSeries + this.APIkey + this.contentToSearch)
      .then(res => {
        console.log(res.data.results);
        this.ContentList= res.data.results;
        console.log(this.ContentList)
      })
    },
  },
}
</script>

<style lang="scss">
@import './style/General';
#app {
  background-color: white;
}
</style>
