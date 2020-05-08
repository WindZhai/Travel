<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" />
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
        <!-- 让下面这句话在有搜索结果时不显示，使用v-show -->
        <li class="search-item border-bottom" v-show="hadNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
  import Bscroll from 'better-scroll'
  export default {
    name: 'CitySearch',
    props: {
      cities: Object
    },
    data () {
      return {
        keyword:'',
        list:[],
        timer:null
      }
    },
    computed:{
      hadNoData () {
        return !this.list.length
      }
    },
    watch:{
      keyword () {
        if(this.timer) {
          clearTimeout(this.timer)
        }
        //添加删除搜索内容后结果清空的效果
        if(!this.keyword) {
          this.list = []
          return
        }
        this.timer = setTimeout(() => {
          const result = []
          for (let i in this.cities){
            this.cities[i].forEach((value)=> {
              if(value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) >-1){
                result.push(value)
              }
            })
          }
          this.list = result
        },100)
      }
    },
    methods: {
      handleCityClick (city) {
        this.$store.commit('changeCity', city)
        // 跳转到首页
        this.$router.push('/')
      }
    },
    // 添加滚动效果
    mounted () {
      this.scroll = new Bscroll(this.$refs.search)
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
   height .72rem
   background $bgColor
   padding 0 .1rem
   .search-input
    box-sizing border-box
    height .62rem
    line-height .62rem
    width 100%
    text-align center
    border-radius .06rem
    color #666
    padding 0 .1rem
  .search-content
   z-index 1
   overflow hidden
   position absolute
   top 1.58rem
   left 0
   right 0
   bottom 0
   background #eee
   .search-item
    line-height .62rem
    padding-left .2rem
    color #666666
    background #fff

</style>
