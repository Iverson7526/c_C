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
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        }
      },
      iconList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      },
      {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      },
      {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
        desc: '游船游艇'
      },
      {
        id: '04',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
        desc: '夏日玩水'
      },
      {
        id: '05',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '水上乐园'
      },
      {
        id: '06',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '亲子游'
      },
      {
        id: '07',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '厦门必游'
      },
      {
        id: '08',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
        desc: '汽车票'
      },
      {
        id: '09',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
        desc: '鼓浪屿'
      },
      {
        id: '10',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
        desc: '全部玩乐'
      }
      ]
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
</style>
