<template>
<div class="search">
  <input type="text" class="search-input" placeholder="输入城市名或拼音"/>
</div>
</template>

<script>
export default{
  name:'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variables.styl'
  .search
    padding: 0 .1rem
    height:.72rem
    background :$bgColor
    text-align:center
    .search-input
      box-sizing:border-box
      height:.62rem
      line-height:.62rem
      width:100%
      padding:0 .1rem
      text-align:center
      border-radius:.06rem
      color: #666
</style>
