<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
    <router-link to='/city'>
    <div class="header-right">
      <span class="iconfont arrowicon">&#xe64a;</span>{{this.$store.state.city}}</div>
    </router-link>
  </div>
</template>

<script>
export default{
  name:'HomeHeader',
  props:{
    city:String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .header
      display:flex
      line-height:$headerHeight
      background:$bgColor
      color:#fff
      .header-left
        width:.64rem
        float:left
      .header-input
        flex:1
        height:.64rem
        line-height:.64rem
        background:#fff
        margin-top:.12rem
        margin-left:.1rem
        border-radius:.1rem
        color:#ccc
      .header-right
        width:1.24rem
        float:right
        text-align:center
        color: #fff
        .arrowicon
          font-size:.24rem
          margin-right:.12rem



</style>
