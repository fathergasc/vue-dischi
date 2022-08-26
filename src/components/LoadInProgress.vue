<template>
  <div id="loading">
    <h1>Caricamento in corso...</h1>
  </div>
</template>

<script>
export default {
 name:'LoadInProgress',
}
</script>

<style lang="scss">
@import '@/styles/general.scss';

#loading {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 8rem;
    height: 100%;
    width: 100%;
    z-index: 999;
    background-color: #1e2d3b;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>