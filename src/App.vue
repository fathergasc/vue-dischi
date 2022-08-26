<template>
  <div id="app">
    <MyHeader />
    <AlbumList />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    AlbumList
  }
}
</script>

<style lang="scss">

@import '@/styles/general.scss';

#app {
  height: 100vh;
}
</style>
