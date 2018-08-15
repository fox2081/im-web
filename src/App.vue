<template>
  <div id="app">
    <img src="./assets/im-icon.png" @click="imConfig.initDirective()" alt="">
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
        a: 1,
        showInit: false
      }
    }
  },
  methods: {}
}
</script>

<style lang="scss">
  @import "assets/css/base";
  @import "assets/css/common";

  #app {
    font-family: 'Microsoft Yahei';
  }
</style>
