<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for= "(page, index) of pages" :key= "index">
        <div class="icon" v-for= "item of page" :key= "item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        }
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-pagination-bullet-active
    background rgba(0,175,190,.8)
  .icons >>> .swiper-pagination-bullet
    width 6px
    height 6px
  .icons >>> .swiper-pagination-bullets
    bottom 6px
  .icons
    height 185px
    padding-top 5px
    text-align center
    .swiper-container
      height 185px
    .icon
      float left
      box-sizing border-box
      width 25%
      height 80px
      padding-top 5px
      .icon-img
        display inline-block
        width 55px
        height 55px
        .icon-img-content
          width 55px
          height 55px
      .icon-desc
        margin-top 5px
        font-size 14px
        text-align center
        color $darkTextColor
        ellipsis()
</style>
