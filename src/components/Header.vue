<template>
  <div class="header d-flex justify-content-between">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
    <div>
      <select name="genere" id="genere" 
      v-model="genreSelected" 
      @change="getGenre">
        <option value="all">all</option>
        <option
          v-for="(genre, index) in geners"
          :value="genre"
          :key="index"
        >
          {{ genre }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: 'header',
  props: ["discList"],
  data(){
    return {
      genreSelected:"all",
    }
  },
  methods: {
    getGenre() {
      this.$emit("getGenre", this.genreSelected);
    },
  },
  computed:{
    geners(){
      const genres=[];
      this.discList.forEach((album)=>{
        if(!genres.includes(album.genre)){
          genres.push(album.genre);
        }
      })
      return genres;
    },
  },
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
