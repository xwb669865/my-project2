<template>
  <div>
     <detail-banner 
       :sightName="sightName"
       :bannerImg="bannerImg"
       :bannerImgs="gallaryImgs"
     ></detail-banner>
     <detail-header></detail-header>
     <div class="content">
        <detail-list :List="List"></detail-list>
     </div>
  </div>

</template>
 
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'

export default {
  name:'Detail',
  components: {
     DetailBanner,
     DetailHeader,
     DetailList
  },
  data (){
    return {
      sightName:'',
      bannerImg:'',
      gallaryImgs: [],
      List: []  
    }
  },
   methods: {
    getDetailInfo () {
      axios.get('/static/mock/detail.json',{
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res){
      res = res.data
      if(res.ret && res.data){
        const data = res.data 
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.List = data.categoryList
      }
    }
  }, 
   mounted (){
    this.getDetailInfo ()
  } 
  
}
  
</script>

<style scoped>
  .content{
    height:2500px;
  }
</style>