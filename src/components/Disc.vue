<template>
  <div id="Disc" class="d-flex flex-column justify-content-around align-items-center">
    <div>
      <img :src="item.poster" alt="">
    </div>
    <h4>{{item.title}}</h4>
    <p>{{item.author}}</p>
  </div>
</template>

<script>

export default {
  name: 'Disc',
  props: ["item"]
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#Disc{
  background-color: #2e3a46;
  padding: 10px;
  width: calc(20% - 20px);
  margin: 10px;
  div{
    width: 70%;
  }
  img{
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  h4{
    color:#fff;
    text-align: center;
  }
  p{
    text-align: center;
    color:#7d7d7c;
  }
}
</style>
