<template>
	<div>
    <div class="banner" @click="handleGalleryShow">
      <img class="banner-img"
      src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg"/>
      <div class="banner-info">
        <div class="banner-title">故宫(AAAAA景区)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe692;</span>12</div>
      </div>
    </div>
    <common-gallery :imgs="imgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default{
  name:'DetailBanner',
  components:{
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      imgs:['http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_350x240_cf4cd08e.png','http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_350x240_cf4cd08e.png']
    }
  },
  methods:{
    handleGalleryShow () {
      this.showGallery=true
    },
    handleGalleryClose () {
      this.showGallery=false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position :relative
  overflow:hidden
  height:0
  padding-bottom:55%
  .banner-img
    width:100%
  .banner-info
    display:flex
    position:absolute
    left:0
    right:0
    bottom:0
    line-height:.6rem
    color: #fff
    background-image: linear-gradient(top,rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.8))
    .banner-title
      flex:1
      font-size: .32rem
      padding: 0 .2rem
    .banner-number
      line-height: .32rem
      height: .4rem
      //(0.6-0.32)/2=0.14rem
      margin-top: .14rem
      padding: 0 .32rem
      border-radius: .2rem
      background: rgba(0, 0, 0,.8)
      font-size: .24rem
      .banner-icon
        font-size: .24rem
</style>
