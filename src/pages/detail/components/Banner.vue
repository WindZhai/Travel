<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="https://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_600x330_37602849.jpg" />
      <div class="banner-info">
        <div class="banner-title">
          北京动物园(AAAA景区)
          </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe609;</span>
          39
          </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
  import CommonGallary from 'common/gallary/Gallary.vue'
  export default {
    name: 'DetailBanner',
    data () {
      return {
        showGallary: false,
        imgs: ['https://img1.qunarzz.com/sight/p0/201308/08/41150dacc0e3a0c8c8d65eac.jpg_600x330_37602849.jpg',
          'https://img1.qunarzz.com/sight/p0/2003/71/7106361cb6c272aaa3.water.jpg_600x330_4cfb45db.jpg']
      }
    },
    methods: {
      handleBannerClick () {
        this.showGallary = true
      },
      handleGallaryClose () {
        this.showGallary = false
      }
    },
    components: {
      CommonGallary
    }
  }
</script>

<style lang="stylus" scoped>
  .banner
   overflow hidden
   height 0
   padding-bottom 55%
   position relative
   .banner-img
    width 100%
   .banner-info
    display flex
    position absolute
    left 0
    right 0
    bottom 0
    line-height .6rem
    color #fff
    background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
    .banner-title
     flex 1
     font-size .32rem
     padding 0 .2rem
    .banner-number
     margin-top .14rem
     padding 0 .4rem
     line-height .32rem
     height .32rem
     border-radius .2rem
     background rgba(0,0,0, .8)
     font-size .24rem
     .banner-icon
      font-size .24rem
</style>
