<template>
  <div class="div2">
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icon></home-icon>
    <home-recommend></home-recommend>
  </div>
</template>

<script>
import HomeHeader from './components/header.vue'
import HomeSwiper from './components/swiper.vue'
import HomeIcon from './components/icons.vue'
import HomeRecommend from './components/Recommend.vue'
export default{
  name: 'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommend
  }
}
</script>

<style lang="stylus" scoped>
</style>
