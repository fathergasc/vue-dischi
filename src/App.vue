<template>
  <div id="app">
    <MyHeader :genresList="genresList"/>
    <AlbumList @genresList="getGenresList" />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  data() {
    return {
      genresList: [],
    }
  },
  components: {
    MyHeader,
    AlbumList
  },
  methods: {
    getGenresList(array) {
      this.genresList = array;
      console.log('genresList in app.vue', this.genresList);
    }
  }
}
</script>

<style lang="scss">

@import '@/styles/general.scss';

#app {
  height: 100vh;
}
</style>
