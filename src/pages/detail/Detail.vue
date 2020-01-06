<template>
  <div>
    <detail-banner></detail-banner>
    
  </div>
</template>

<script>
//webpack.base里面已经设置好了路径
import DetailBanner from './components/Banner'
export default{
  name:'Detail',
  components:{
    DetailBanner

  }
}
</script>

<style lang="stylus" scoped>
</style>
