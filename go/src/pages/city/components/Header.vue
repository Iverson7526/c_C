<template>
  <div class="header">
    城市选择
    <router-link to='/'>
      <div class="iconfont icon-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default{
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  .header
    position relative
    height 40px
    background $bgColor
    text-align center
    line-height 40px
    color #ffffff
    font-size 16px
    .icon-back
      position absolute
      width 40px
      height 40px
      top 0
      left 0
      color #fff
      font-size 20px
</style>
