<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
        <!-- slides -->
        <swiper-slide v-for="item in list":key="item.id">
          <img class="swiper-img" :src="item.imgUrl"/>
        </swiper-slide>

        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>

<script>
export default{
name:'HomeSwiper',
data:function(){
  return{
    swiperOption:{
      pagination:'.swiper-pagination',
      loop:true
    },
  }
},
computed:{
  showSwiper () {
    return this.list.length
  }
},
props:{
  list:Array
}
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet
    background:#fff
  .wrapper
    overflow:hidden
    width:100%
    height:0
    padding-bottom:30%
    .swiper-img
      width:100%


</style>
