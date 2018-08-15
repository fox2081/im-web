<template>
  <div class="init-modal">
    <div><img src="../../assets/img/im-list-loading.gif" alt=""></div>
    <p>正努力加载聊天窗口...</p>
  </div>
</template>

<script>
export default {
  name: 'im-init'
}
</script>

<style lang="scss" scoped>
  .init-modal {
    position: fixed;
    width: 340px;
    height: 110px;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    margin: auto;
    background: #fff;
    box-shadow: 0 0 20px rgba(0, 0, 0, .5);
    z-index: 99;
    border-radius: 4px;
    text-align: center;
    > div > img {
      margin-top: 10px;
    }
    > p {
      font-size: 16px;
      word-spacing: 8px;
      letter-spacing: 2px;
      margin: 0;
    }
  }
</style>
