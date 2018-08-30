<template>
  <div class="im-modal scale-in" v-bind:class="true" v-show="false">
    <div class="bg-mask" v-show="true"></div>
    <div class="modal-main">
      <div class="ml-header" v-show="dialog.s.header">
        <span class="title" v-show="dialog.title || '温馨提示'"></span>
        <a class="close" @click="close()" v-show="dialog.s.close">×</a>
      </div>
      <div class="ml-body" v-show="dialog.s.body"></div>
      <div class="ml-footer" v-show="dialog.s.footer">
        <button class="ok" @click="ok()" v-bind="dialog.okBtn" v-show="dialog.hideBtn.ok"></button>
        <button class="cancel" @click="cancel()" v-bind="dialog.cancelBtn || '取消'"
                v-show="dialog.hideBtn.cancel"></button>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'im-modal',
  data () {
    return {
      dialog: {
        okBtn: '确定',
        hideBtn: {},
        s: {}
      }
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
