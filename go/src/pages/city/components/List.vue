<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">
          当前城市
        </div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">厦门</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">
          热门城市
        </div>
        <div class="button-list">
          <div class="button-wrapper" v-for="item of hotCities" :key="item.id">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">
          {{key}}
        </div>
        <div class="item-list">
          <div class="item border-bottom" v-for="itemInner of item" :key="itemInner.id">{{itemInner.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const dom = this.$refs[this.letter][0]
        this.scroll.scrollToElement(dom)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .border-topbottom
    &:before,&:after
      border-color #ccc
  .border-bottom
    &:before
      border-color #ccc
  .list
    position absolute
    top 75px
    left 0
    right 0
    bottom 0
    overflow hidden
    .title
      line-height 27px
      background #eee
      color #666666
      padding-left 10px
      font-size 13px
    .button-list
      overflow hidden
      padding 5px 30px 5px 5px
      .button-wrapper
        float left
        width 33.333%
        .button
          margin 5px
          padding 1px 0
          line-height 22px
          text-align center
          border 1px solid #ccc
          border-radius 3px
    .item-list
      .item
        line-height 38px
        color #666
        padding-left 10px
</style>
