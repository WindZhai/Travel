<template>
  <div>
      <div class="header">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
      <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/游玩景点/美食</div>
      <router-link to="/city">
        <div class="header-right">{{this.$store.state.city}}<span class="iconfont arrow-icon">&#xe64a;</span></div>
      </router-link>
      </div>
  </div>
</template>

<script>
export default{
  name: 'HomeHeaders'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
   .header
    display: flex
    line-height: $headerHeight
    background : $bgColor
    color : #fff
   .header-left
    width .64rem
    float left
    .back-icon
      text-align center
      font-size .4rem
   .header-input
    flex : 1
    height .64rem
    line-height .64rem
    background #ffffff
    border-radius .1rem
    margin-top .11rem
    margin-left .2rem
    color #cccccc
    padding-left .2rem
   .header-right
    width: 1.24rem
    float:right
    text-align center
    color #FFFFFF
    .arrow-icon
      font-size .1rem
</style>
