<template>
  <div class="header">
    <div class="header-left">返回</div>
    <div class="header-input">输入城市/景点/游玩主题</div>
    <div class="header-right">城市</div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
.header
  display flex
  height 43px
  line-height 43px
  background #00bcd4
  color #fff
  .header-left
    float left
    width 32px
  .header-input
    flex 1
    height 31px
    line-height 32px
    margin 6px 10px
    background #ffffff
    border-radius 5px
    color #ccc
  .header-right
    float right
    width 62px
    text-align center
</style>
