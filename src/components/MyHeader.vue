<template>
  <header class="px-3 d-flex justify-content-between align-items-center">
    <img id="spotify-logo" src="@/assets/images/logo.svg" alt="">
    <select>
      <option value="">Scegli un genere</option>
      <option v-for="(genre, index) in genresList" :key="index" :value="genre">{{genre}}</option>
    </select>
  </header>
</template>

<script>

export default {
 name: 'MyHeader',
 props: {
  genresList: {
   type: Array,
  }
 },
}
</script>

<style lang="scss">
@import '@/styles/general.scss';

header {
    height: 100px;
    background-color: #2e3a46;
    line-height: 100px;

    img {
        height: 50%;
        width: auto;
        padding-left: 30px;
        
    }
}

</style>