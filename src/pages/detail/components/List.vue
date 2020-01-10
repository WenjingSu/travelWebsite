<template>
  <div>
    <div class="item" v-for="(item,index) in list":key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children">
          <!-- <div v-if="item.children.children" class="item-children">
            <detail-list :list="item.children.children"></detail-list>
          </div> -->
        </detail-list>
      </div>

    </div>
  </div>
</template>

<script>
export default{
  name:'DetailList',
  props : {
    list:Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    line-height : .8rem
    font-size : .32rem
    padding : .2rem
    .item-title-icon
      position : relative
      left : .2rem
      top : .2rem
      padding : 0 .2rem
      display : inline-block
      width : .36rem
      height : .46rem
      background : url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0-.45rem no-repeat
      margin-right : .1rem
      background-size : .4rem 3rem
  .item-children
    padding : 0 .2rem
</style>
