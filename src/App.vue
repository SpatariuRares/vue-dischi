<template>
  <div id="app">
    <Header/>
    <main class="d-flex">
      <Discs/>
    </main>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Discs from './components/Discs.vue'

export default {
  name: 'App',
  components: {
    Header,
    Discs
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

main{
  background-color: #1e2d3b;
  height:calc(100vh - 70px);
  overflow: auto;
}
</style>
