<template>
  <main>
    <div v-for= "(content, index) in ContentList" :key="index">
      <Content :info= content />
    </div>  
  </main>
</template>

<script>
import Content from './Content.vue';
import axios from 'axios';

export default {
  name: 'ContentView',
  components: {
    Content
  },
  data() {
      return {
        APIurl: 'https://api.themoviedb.org/3/search/movie?',
        APIkey: 'api_key=ddb4c15369c26b2f75ed68bdbbe010b8&language=it-IT&query=',
        APIquery: 'rick',
        ContentList: ''
      }
  },
  methods : {
    getContentList() {
      axios.get(this.APIurl + this.APIkey + this.APIquery)
      .then(res => {
        console.log(res.data.results);
        this.ContentList= res.data.results;
        console.log(this.ContentList)
      })
    }
  },
  mounted() {
    this.getContentList()
  }
}
</script>

<style lang="scss">
@import '../style/General';

</style>