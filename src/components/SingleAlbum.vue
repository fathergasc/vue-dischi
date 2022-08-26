<template>

  <div class="col">
    <div class="album text-center">
        <img :src="album.poster">
        <span class="uppercase fs-5 text-white fw-bold py-2">{{ album.title }}</span>
        <span class="fs-6 text-white-50 pt-2">{{album.author}}</span>
        <span class="fs-6 text-white-50">{{album.year}}</span>
    </div>
  </div>
    
</template>

<script>
export default {
 name: 'SingleAlbum',
 props: {
   album: {
     type: Object,
   }
 },
}
</script>

<style lang="scss">
span {
  display: block;
}

.uppercase {
  text-transform: uppercase;
}

</style>