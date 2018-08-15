<template>
  <div class="im-main">
    <im-init v-if="config.showInit"></im-init>
    <im-window></im-window>
    <im-notice></im-notice>
  </div>
</template>

<script>
import imInit from './dir/im-init'
import imWindow from './dir/im-window'
import imNotice from './dir/im-notice'

export default {
  name: 'imDirective',
  components: {
    imInit,
    imWindow,
    imNotice
  },
  props: ['config'],
  data () {
    return {}
  },
  methods: {
    initDirective () {
      let vm = this
      vm.config.showInit = true
    }
  },
  created () {
    let vm = this
    vm.config.showInit = false
    vm.config.initDirective = this.initDirective
  }
}
</script>

<style lang="scss" scoped>
  .im-main {
    width: 100%;
    height: 100%;
  }
</style>
