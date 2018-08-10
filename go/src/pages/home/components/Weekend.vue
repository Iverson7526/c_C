<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for= "item of weekendList" :key= "item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src= "item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Weekend',
  data () {
    return {
      weekendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1711/15/1cdd5ee885686b.jpg_r_640x214_46768064.jpg',
        title: '世茂云上厦门观光厅',
        desc: '体验文化盛宴，尽享东方神韵'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1711/15/1cdd5ee885686b.jpg_r_640x214_46768064.jpg',
        title: '世茂云上厦门观光厅',
        desc: '体验文化盛宴，尽享东方神韵'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1711/15/1cdd5ee885686b.jpg_r_640x214_46768064.jpg',
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
  line-height 40px
  background #eeeeee
  text-indent 10px
.item
  border-bottom 5px solid #f5f5f5
  .item-img-wrapper
    height 0
    padding-bottom 33.5%
    overflow hidden
    .item-img
      width 100%
  .item-info
    flex 1
    min-width 0
    padding 5px
    .item-title
      line-height 30px
      font-size 14px
      ellipsis()
    .item-desc
      line-height 24px
      font-size 12px
      color #616161
      ellipsis()
</style>
