<template>
  <div class="header">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
  </div>
</template>

<script>
export default {
  name: 'header',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  background-color: rgba(46,58,70,255)
;
  height: 70px;
  width: 100%;
  padding: 10px;
  img{
    height: 100%;
    object-fit: contain;
  }
}
</style>
