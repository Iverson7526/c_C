<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont icon-back">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont icon-input">&#xe670;</span>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{this.city}}
      <span class="iconfont icon-arrow">&#xe6aa;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display flex
  height 44px
  line-height 44px
  background $bgColor
  color #fff
  .header-left
    float left
    width 32px
    .icon-back
      text-align center
      font-size 20px
  .header-input
    flex 1
    height 30px
    line-height 30px
    margin 7px 0 0 10px
    padding-left 10px
    background #ffffff
    border-radius 3px
    color #ccc
    .icon-input
      float left
      margin-right 3px
  .header-right
    float right
    width 62px
    text-align center
    .icon-arrow
      float right
      margin 0px 5px 0 -10px
      font-size 18px
</style>
