<template>
  <main>
    <div class="content-wrapper">
      <Content v-for= "(content, index) in ContentList" :key="index" :info= content />
    </div>  
  </main>
</template>

<script>
import Content from './Content.vue';

export default {
  name: 'ContentView',
  components: {
    Content
  },
  props: ['ContentList'],
}
</script>

<style lang="scss">
@import '../style/General';
  main {
    height: calc(100vh - 70px);
    background-color: grey;
    overflow: hidden;

    .content-wrapper {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
    }
  }
</style>