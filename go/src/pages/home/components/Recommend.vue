<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for= "item of recommendList" :key= "item.id">
        <img class="item-img" :src= "item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Recommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  margin-top 5px
  line-height 40px
  background #eeeeee
  text-indent 10px
.item
  display flex
  height 95px
  overflow hidden
  .item-img
    width 85px
    height 85px
    padding 5px
  .item-info
    flex 1
    min-width 0
    padding 5px
    .item-title
      line-height 27px
      font-size 16px
      ellipsis()
    .item-desc
      line-height 24px
      color #ccc
      ellipsis()
    .item-button
      padding 0 5px
      margin-top 8px
      background #ff9300
      border-radius 3px
      color #fff
</style>
