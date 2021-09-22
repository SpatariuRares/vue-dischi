<template>
  <div id="Discs" class="container d-flex ">
    <div class="row">
      <Disc
        v-for="(Disc,index) in discList" :key="index"
        :item="Disc"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Disc from "./Disc.vue";
export default {
  name: 'Discs',
  components: {
    Disc,
  },
  data(){
    return {
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
      discList:[],
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
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
