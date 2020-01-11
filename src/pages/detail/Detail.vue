<template>
  <div>
    <detail-banner
    :sightName="sightName"
    :bannerImg="bannerImg"
    :galleryImgs="galleryImgs"
    ></detail-banner>
    <detail-header></detail-header>

    <div class="content">
      <detail-list :list="categoryList"></detail-list>
    </div>
  </div>
</template>

<script>
//webpack.base里面已经设置好了路径
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default{
  name:'Detail',
  components:{
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName:'',
      bannerImg:'',
      galleryImgs:[],
      categoryList:[]
      // categoryList:[{
      //   title:'成人票',
      //   children : [{
      //     title:'成人三馆联票'
      //   },{
      //     title:'成人五馆联票',
      //     children :[{
      //       title:'成人五馆联票某一连锁店销售'
      //     }]
      //   }]
      // },
      // {
      //   title:'儿童票'
      // },
      // {
      //   title:'学生票'
      // },
      // {
      //   title:'特价票'
      // }]
    }
  },
  methods : {
    getDetailInfo () {
      axios.get('/api/detail.json',{
        params:{
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res=res.data
      if(res.ret&&res.data){
        const data=res.data
        this.sightName=data.sightName
        this.bannerImg=data.bannerImg
        this.galleryImgs=data.galleryImgs
        this.categoryList=data.categoryList
      }
    },
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height:50rem
</style>
