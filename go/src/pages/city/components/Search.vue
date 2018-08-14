<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="请输入城市或景点">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height 30px
    padding 0 10px 5px
    background $bgColor
    .search-input
      box-sizing border-box
      width 100%
      height 30px
      padding 0 5px
      line-height 30px
      border-radius 3px
      text-align center
      color #666
</style>
