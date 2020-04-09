<template>
  <div class="wrapper">
<swiper ref="mySwiper" :options="swiperOptions">
    <swiper-slide v-for= "item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" />
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
 </swiper>
 </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        loop:true
      },
      swiperList:[{
        id: '0001',
        imgUrl: "https://imgs.qunarzz.com/sight/source/1505/e3/e9761259adfc1d.jpg_r_640x214_21b96532.jpg"
      }, {
        id: '0002',
        imgUrl: "https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg"
      }]
    }
  }
}
</script>

<style lang="stylus" scoped="scoped">
  .wrapper >>> .swiper-pagination-bullet-active
   background #FFFFFF
  .swiper-img
    width 100%
   .wrapper{
     width 100%
     height 0
     overflow hidden
     padding-bottom 31.25%
   }
</style>
