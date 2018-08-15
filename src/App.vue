<template>
  <div id="app">
    <img src="./assets/logo.png">
    <im-directive v-bind:config="imConfig"></im-directive>
  </div>
</template>

<script>
import imDirective from './components/im-directive'

export default {
  name: 'App',
  components: {
    imDirective
  },
  data () {
    return {
      imConfig: {
        a: 1
      }
    }
  }
}
</script>

<style lang="scss">
  @import "assets/css/base";
  @import "assets/css/common";

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
