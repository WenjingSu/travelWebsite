<template>
  <div class="div2">
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icon :list="iconList"></home-icon>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/header.vue'
import HomeSwiper from './components/swiper.vue'
import HomeIcon from './components/icons.vue'
import HomeRecommend from './components/Recommend.vue'
import HomeWeekend from './components/Weekend.vue'
import axios from 'axios'
export default{
  name: 'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    }
  },
  methods:{
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSuccess)
    },
    getHomeInfoSuccess (res) {
      res=res.data
      if(res.ret&&res.data){
        // console.log(res)
        const data=res.data
        this.swiperList=data.swiperList
        this.iconList=data.iconList
        this.recommendList=data.recommendList
        this.weekendList=data.weekendList
      }
    }
  },
  mounted (){
    this.getHomeInfo()
  }
}
</script>

<style lang="stylus" scoped>
</style>
