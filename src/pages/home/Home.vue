<template>
  <div class="div2">
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icon></home-icon>
  </div>
</template>

<script>
import HomeHeader from './components/header.vue'
import HomeSwiper from './components/swiper.vue'
import HomeIcon from './components/icons.vue'
export default{
  name: 'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcon
  }
}
</script>

<style lang="stylus" scoped>
</style>
