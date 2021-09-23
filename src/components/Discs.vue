<template>
  <div id="Discs">
      <Disc
        v-for="(Disc,index) in filterlist" :key="index"
        :item="Disc"
      />
      <Loader
      :flag="loading"/>
  </div>
</template>

<script>

import Disc from "./Disc.vue";
import Loader from "./Loader.vue";
export default {
  name: 'Discs',
  props: ["discList","filtergener","loading","filterartist"],
  components: {
    Disc,
    Loader,
  },
  data(){
    return {
      APIUrl:"https://flynn.boolean.careers/exercises/api/array/music",
    }
  },
  computed:{
    filterlist(){
      let filterlist=this.discList.filter((ris)=>{
        if(this.filtergener=="all") return true
        else if(ris.genre==this.filtergener)return true;
        else return false;
      });
      filterlist=filterlist.filter((ris)=>{
        console.log(ris.author)
        if(this.filterartist=="all") return true
        else if(ris.author==this.filterartist)return true;
        else return false;
      });
      return filterlist;
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#Discs{
  width: 70%;
  margin: 0 auto; 
  display:flex;
  flex-wrap: wrap;
}
</style>
