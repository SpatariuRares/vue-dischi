<template>
  <div id="app">
    <Header
      :discList="disclist"
      @getGenre="getGenre"
      @getArtist="getArtist"
    />
    <main>
      <Discs
      :discList="disclist"
      :loading="loader"
      :filtergener="filtergener"
      :filterartist="filterartist"
      />
    </main>
  </div>
</template>

<script>
import axios from "axios";
import Header from './components/Header.vue'
import Discs from './components/Discs.vue'

export default {
  name: 'App',
  components: {
    Header,
    Discs
  },
  data(){
    return {
      disclist:[],
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
      loader: true,
      filtergener:"all",
      filterartist:"all",
    }
  },
  created(){
    this.getdisc();
  },
  methods:{
    getdisc(){
      axios.get(this.APIUrl).then((res)=>{
        this.disclist = res.data.response;
        this.loader=false;
      })
    },
    getGenre(gener){
      this.filtergener=gener;
    },
    getArtist(artist){
      this.filterartist=artist;
    }
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

main{
  background-color: #1e2d3b;
  height:calc(100vh - 70px);
    padding:2%;
}
</style>
