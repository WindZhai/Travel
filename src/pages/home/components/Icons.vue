<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key='item.id'>
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" />
           </div>
           <p class="icon-desc">{{item.desc}}</p>
        </div>
       </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/67370daeaa1a8ac24a6c7930f74fee0c.png',
        desc: '发现王国'
      }, {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
        desc: '大连圣亚'
      },{
        id: '0004',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b71c1387a921ccf9c6edc7e8def3da90.png',
        desc: '大连森林动物园'
      },{
        id: '0005',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
        desc: '踏青赏花'
      },{
        id: '0007',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/a40ee278d67000f2a29d2e20f6a029b3.png',
        desc: '自然风光'
      },{
        id: '0008',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/3a0879f224e0aca97843bff78cabac3a.png',
        desc: '大连必游'
      },{
        id: '0009',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item,index) =>{
        const page = Math.floor(index/8)
          if(!pages[page]){
            pages[page] =[]
          }
          pages[page].push(item)
      })
      return pages;
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
   height 0
   padding-bottom 50%
  .icon
   height 0
   overflow hidden
   float left
   width 25%
   padding-bottom 25%
   position relative
   .icon-img
    position absolute
    top 0
    left 0
    right 0
    bottom .44rem
    box-sizing border-box
    padding .1rem
    .icon-img-content
      height 100%
      display block
      margin 0 auto
   .icon-desc
    position absolute
    left 0
    right 0
    bottom 0
    line-height .44rem
    height .44rem
    color $darkTextColor
    text-align center
    ellipsis()
</style>
