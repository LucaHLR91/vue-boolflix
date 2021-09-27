<template>
  <main>
    <div>
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

</style>