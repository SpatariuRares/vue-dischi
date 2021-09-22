<template>
  <div id="Discs" class="d-flex flex-wrap">
      <Disc
        v-for="(Disc,index) in discList" :key="index"
        :item="Disc"
      />
      <Loader
      :flag="loading"/>
  </div>
</template>

<script>
import axios from "axios";
import Disc from "./Disc.vue";
import Loader from "./Loader.vue";
export default {
  name: 'Discs',
  components: {
    Disc,
    Loader,
  },
  data(){
    return {
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
      discList:[],
      loading: true,
    }
  },
  created(){
    this.getdisc();
  },
  methods:{
    getdisc(){
      axios.get(this.APIUrl).then((res)=>{
        console.log(res.data.response);
        this.discList = res.data.response;
        this.loading=false;
      })
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#Discs{
  width: 70%;
  padding:5%;
  margin: 0 auto; 
}
</style>
