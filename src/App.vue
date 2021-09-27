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
      MoviesList: [],
      TvSeriesList: [],
      ContentList: [],
      APIurlMovies: 'https://api.themoviedb.org/3/search/movie?',
      APIurlTvSeries: 'https://api.themoviedb.org/3/search/tv?',
      APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT&query=',
    }
    
  },
  methods: {
    startSearch(contentToSearch) {
      this.contentToSearch = contentToSearch;
      this.ContentList= [];
      this.getMovies();
      this.getTvSeries();
      console.log(this.ContentList)
    },
    getMovies() {
      axios.get(this.APIurlMovies + this.APIkey + this.contentToSearch)
      .then(res => {
        this.MoviesList= res.data.results;
        this.ContentList= [...this.ContentList, ...this.MoviesList];
        console.log(this.MoviesList)
      })
    },
    getTvSeries() {
      axios.get(this.APIurlTvSeries + this.APIkey + this.contentToSearch)
      .then(res => {
        this.TvSeriesList= res.data.results;
        this.ContentList= [...this.ContentList, ...this.TvSeriesList];
        console.log(this.TvSeriesList)
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
