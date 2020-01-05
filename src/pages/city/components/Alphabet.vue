<template>
  <ul class="list">
    <li class="item"
    v-for="item in letters":key="item" :ref="item"
    @click="handleLetterClick"
    @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd">
    {{item}}</li>
  </ul>
</template>

<script>
export default{
  name:'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus:false,
      startY:0,
      timer:null
    }
  },
  updated () {
    const startY=this.$refs['A'][0].offsetTop
  },
  computed : {
    letters () {
      const letters=[]
      for(let i in this.cities){
        //letters:['A','B'...]
        letters.push(i)
      }
      return letters
    }
  },
  methods:{
    handleLetterClick (e) {
      this.$emit('change',e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus=true
    },
    handleTouchMove (e) {
      if(this.touchStatus){
        //函数截流
        if(this.timer){
          clearTimeout(this.timer)
        }
        this.time=setTimeout(()=>{
          const touchY=e.touches[0].clientY-79
          const index=Math.floor((touchY-this.startY)/20)
          if(index >= 0 && index < this.letters.length){
            this.$emit('change',this.letters[index])
          }
        },16)
        
      }
    },
    handleTouchEnd () {
      this.touchStatus=false
    },
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/variables.styl"
  .list
    display:flex
    flex-direction:column
    justify-content:center
    position:absolute
    top:1.58rem
    bottom:0
    right:0
    width:.4rem
    .item
      line-height:.4rem
      text-align:center
      color:$bgColor
</style>
