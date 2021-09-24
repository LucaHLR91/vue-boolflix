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
      APIurl: 'https://api.themoviedb.org/3/search/movie?',
      APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT&query=',
      APIquery: 'Lord of the rings',
    }
    
  },
  methods: {
    startSearch(contentToSearch) {
      this.contentToSearch = contentToSearch;
      this.getContentList()
      console.log(contentToSearch)
    },
    getContentList() {
      axios.get(this.APIurl + this.APIkey + (!this.contentToSearch ? this.APIquery : this.contentToSearch))
      .then(res => {
        console.log(res.data.results);
        this.ContentList= res.data.results;
        console.log(this.ContentList)
      })
    },
  },
  mounted() {
    this.getContentList()
  }
}
</script>

<style lang="scss">
@import './style/General';
#app {
  background-color: white;
}
</style>
