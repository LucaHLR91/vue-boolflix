<template>
  <div id="app">
    <Header />
    <ContentView />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import ContentView from './components/ContentView.vue'


export default {
  name: 'App',
  components: {
    Header,
    ContentView
  },
}
</script>

<style lang="scss">
@import './style/General';
#app {
  
}
</style>
