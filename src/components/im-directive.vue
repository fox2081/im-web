<template>
  <div class="im-main">
    hola {{config.a}}
  </div>
</template>

<script>
export default {
  name: 'imDirective',
  props: ['config']
}
</script>

<style lang="scss" scoped>
  .im-main {
    width: 100%;
    height: 100%;
  }
</style>
