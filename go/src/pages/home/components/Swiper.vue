<template>
  <div class="wrapper">
    <swiper :options="swiperOption"  v-if="looooop">
      <!-- slides -->
      <swiper-slide class="swiper-slide" v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"  alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        autoplay: {
          delay: 2500,
          disableOnInteraction: false
        },
        loop: true
      }
    }
  },
  computed: {
    looooop () {
      // 使swiper的loop生效
      return this.swiperList.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background #fff
  .wrapper >>> .swiper-pagination-bullet
    width 6px
    height 6px
  .wrapper >>> .swiper-pagination-bullets
    bottom 6px
  // swiper情况特殊 占位与完整显示 分开完成
  // 占位由最外层容器完成  图片完整显示由图片节点及其父节点组合完成
  // 完整显示需求：图片节点 absolute+宽高百分百 && 某个长辈节点 relative+padding-bottom
  .wrapper
    width 100%
    height 0
    overflow hidden
    padding-bottom 27.25%
    .swiper-slide
      padding-bottom 27.25%
      .swiper-img
        position absolute
        width 100%
        height 100%
</style>
