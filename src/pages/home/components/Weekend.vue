<template>
  <div>
    <div class="recommend-title">周末去哪儿</div>
    <ul>
    	<li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
        <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default{
    name: 'HomeWeekend',
    data () {
      return {
        recommendList: [ {
          id: '0001',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0002',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0003',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
          title: '大连森林动物园',
          desc: '与可爱温顺的羊驼亲密接触'
        }, {
          id: '0004',
          imgUrl: 'https://imgs.qunarzz.com/sight/source/1812/b4/e9d7f043c4fadf.jpg_r_640x214_713df0cf.jpg',
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
   .item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 33.9%
  .item-img
   width 100%
  .item-info
   padding .1rem
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
