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
import ImCore from 'im-core/src/im-core'

function init () {
  let IM = new ImCore({
    showLog: true
  })

  console.log('IM', IM)

  IM.api.connect()

  IM.wsOn('error', (e) => {
    console.log('get event error:', e)
  })

  IM.wsOn('open', (e) => {
    console.log('get event open:', e)
    IM.send({
      i: 1,
      t: 1,
      r: ['u1'],
      c: 'Hola'
    })
  })

  IM.on('aaa', (args) => {
    console.log('aaa', args)
  })
}

init()

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
  mounted () {
    let _self = this
    _self.config.showInit = false
    _self.config.initDirective = this.initDirective

    function initIm () {
      let IM = new ImCore({
        showLog: true
      })

      console.log('IM', IM)

      IM.api.connect()

      IM.on('error', (e) => {
        console.log('get event error:', e)
      })

      IM.on('open', (e) => {
        console.log('get event open:', e)
        IM.send({
          i: 1,
          t: 1,
          r: ['u1'],
          c: 'Hola'
        })
      })
    }

    function init () {
      initIm()
    }

    init()
  }
}
</script>

<style lang="scss" scoped>
  .im-main {
    width: 100%;
    height: 100%;
  }
</style>
