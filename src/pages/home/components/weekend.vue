<template>
<div>
  <div class="title">周末去哪儿</div>
  <ul>
    <li class="item border-bottom" v-for="item in recommendList":key="item.id">
      <div class="item-img-wrapper">
        <img class="item-img" :src="item.imgUrl"/>
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </li>
  </ul>
</div>

</template>

<script>
export default{
  name:'HomeWeekend',
  data (){
    return{
      recommendList:[{
        id:'0001',
        imgUrl:'https://imgs.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        title:'故宫',
        desc:'世界五大宫之首，穿越与您近在咫尺'
      },{
        id:'0002',
        imgUrl:'https://imgs.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
        title:'故宫',
        desc:'世界五大宫之首，穿越与您近在咫尺'
      },{
        id:'0003',
        imgUrl:'https://imgs.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
        title:'故宫',
        desc:'世界五大宫之首，穿越与您近在咫尺'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
  line-height:.8rem
  background:#eee
  text-indent:.10rem
.item-img-wrapper
  overflow:hidden
  height:0
  padding-bottom:33.4%
  .item-img
    width:100%
.item-info
  padding :.1rem
  .item-title
    line-height:.54rem
    font-size:.32rem
    ellipsis()
  .item-desc
    line-height :.4rem
    color:#ccc
    ellipsis()
</style>
