<template>
  <div id="Loader" v-if="flag">
  <svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 477.867 477.867" style="enable-background:new 0 0 477.867 477.867;" xml:space="preserve">
		<path d="M472.184,4.347c-3.631-3.209-8.441-4.75-13.261-4.25l-307.2,34.133c-8.647,0.957-15.19,8.265-15.189,16.964V355.34
			c-15.468-9.256-33.174-14.102-51.2-14.012C38.281,341.329,0,371.946,0,409.595s38.281,68.267,85.333,68.267
			s85.333-30.601,85.333-68.267V151.889l273.067-30.413v199.68c-15.473-9.238-33.179-14.066-51.2-13.961
			c-47.053,0-85.333,30.618-85.333,68.267c0,37.649,38.281,68.267,85.333,68.267s85.333-30.601,85.333-68.267v-358.4
			C477.866,12.208,475.8,7.584,472.184,4.347z"/>
  </svg>
  </div>
</template>

<script>

export default {
  name: 'Loader',
  props: ["flag"]
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#Loader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color:#fff;
  display: flex;
  justify-content: center;
  align-items: center;
  svg{
    width: 10%;
    -webkit-animation: scale-down-center 0.4s ease-in-out infinite alternate both;
    animation: scale-down-center 0.4s ease-in-out infinite alternate both;
  }
  @-webkit-keyframes scale-down-center {
  0% {
    -webkit-transform: scale(1);
            transform: scale(1);
  }
  100% {
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
}
@keyframes scale-down-center {
  0% {
    -webkit-transform: scale(1);
            transform: scale(1);
  }
  100% {
    -webkit-transform: scale(0.5);
            transform: scale(0.5);
  }
}
}
</style>
