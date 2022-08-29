<template>
  <header class="px-3 d-flex justify-content-between align-items-center">
    <img id="spotify-logo" src="@/assets/images/logo.svg" alt="">
    <SelectGenre />
  </header>
</template>

<script>
import SelectGenre from './SelectGenre.vue'

export default {
 name: 'MyHeader',
 components: {
  SelectGenre
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