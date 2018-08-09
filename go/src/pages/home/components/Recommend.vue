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
  data () {
    return {
      recommendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_200x200_f62f78bd.jpg',
        title: '世茂云上厦门观光厅',
        desc: '体验文化盛宴，尽享东方神韵'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_200x200_f62f78bd.jpg',
        title: '世茂云上厦门观光厅',
        desc: '体验文化盛宴，尽享东方神韵'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/7d/7dca9c37a87479eba3.img.jpg_200x200_f62f78bd.jpg',
        title: '世茂云上厦门观光厅',
        desc: '体验文化盛宴，尽享东方神韵'
      }]
    }
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
