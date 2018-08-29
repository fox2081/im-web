<template>
  <div class="im-left-bar">
    <div class="self-avatar mg-t15 mg-b10" title="">
      <img src="" alt="">
    </div>
    <ul>
      <li v-for="(tab, index) in tabList" v-bind:key="index">
        <i v-bind:class="tab.active ? tab.iconActive : tab.icon" @click="switchTab(index)" v-bind:title="tab.name"></i>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'im-left-bar',
  data () {
    return {
      tabList: [
        {
          name: '消息',
          tab: 'msg',
          active: false,
          icon: '',
          iconActive: ''
        },
        {
          name: '找老师',
          tab: 'qna',
          active: false,
          icon: '',
          iconActive: ''
        },
        {
          name: '通讯录',
          tab: 'friend',
          active: false,
          icon: '',
          iconActive: ''
        },
        {
          name: '群组',
          tab: 'group',
          active: false,
          icon: '',
          iconActive: ''
        }
      ]
    }
  },
  methods: {
    switchTab (argIndex) {
      this.tabList.forEach((item, index) => {
        item.active = (index === argIndex)
      })
    }
  },
  mounted () {}
}
</script>

<style lang="scss" scoped>

</style>
