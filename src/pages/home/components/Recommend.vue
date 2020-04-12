<template>
  <div>
    <div class="recommend-title">猜你喜欢</div>
    <ul>
    	<li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详细</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default{
    name: 'HomeRecommend',
    data () {
      return {
        recommendList: [ {
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/1910/80/805d5dc05ab054c2a3.img.jpg_200x200_e5d89794.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/1910/80/805d5dc05ab054c2a3.img.jpg_200x200_e5d89794.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/1910/80/805d5dc05ab054c2a3.img.jpg_200x200_e5d89794.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0004',
          imgUrl: 'https://imgs.qunarzz.com/sight/p0/1910/80/805d5dc05ab054c2a3.img.jpg_200x200_e5d89794.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }]
      }
    }
  }
</script>

<style lang="stylus" scoped="">
  @import '~styles/mixins.styl'
  .recommend-title
   line-height .8rem
   background #eee
   text-indent .2rem
   margin-top .2rem
  .item
   display flex
   height 1.9rem
   overflow hidden
   .item-img
    width 1.7rem
    height 1.7rem
    padding .1rem
   .item-info
    flex 1
    padding .1rem
    min-width 0
    .item-title
     line-height .54rem
     font-size .32rem
     ellipsis()
    .item-desc
     line-height .4rem
     color #ccc
     ellipsis()
    .item-button
     background #ff9300
     padding 0 .16rem
     border-radius .06rem
     margin-top .2rem
     color #FFFFFF
     line-height .44rem
</style>
