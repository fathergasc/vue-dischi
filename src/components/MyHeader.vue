<template>
  <header>
    <img id="spotify-logo" src="@/assets/images/logo.svg" alt="">
  </header>
</template>

<script>
export default {
 name: 'MyHeader',
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