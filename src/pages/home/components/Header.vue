<template>
  <div>
      <div class="header">
      <div class="header-left">返回</div>
      <div class="header-input">输入城市/游玩景点</div>
      <div class="header-right">城市</div>
      </div>
  </div>
</template>

<script>
export default{
  name: 'HomeHeaders'
}
</script>

<style lang="stylus" scoped>
   .header
    display: flex
    line-height: 0.86rem
    background : #00bcd4
    color : #fff
   .header-left
    width .64rem
    float left
   .header-input
    flex : 1
    height .64rem
    line-height .64rem
    background #ffffff
    border-radius .1rem
    margin-top .11rem
    margin-left .2rem
    color #cccccc
   .header-right
    width: 1.24rem
    float:right
    text-align center
</style>
