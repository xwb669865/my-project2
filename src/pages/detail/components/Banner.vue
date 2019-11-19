<template>
  <div>
   <div>
     <div class="banner" @click="handleBannerClick">
       <img class="banner-img" :src="bannerImg" />
       <div class="banner-info">
          <div class="banner-title">
            {{this.sightName}}
          </div>
          <div class="banner-number">
           {{this.bannerImgs.length}}
          </div>
        </div>
      </div>
    
    </div>
     <fade-animation>
      <common-gallary 
      :imgs="bannerImgs"
      v-show="showGallary"
      @close="handleGallaryClose"
      ></common-gallary>
     </fade-animation>
  </div>
</template>
 
<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name:'DetailBanner',
  props: {
    sightName: String,
    bannerImg:String,
    bannerImgs: Array,
  },
  data (){
    return {
      showGallary: false,
    }
  },
  methods: {
    handleBannerClick (){
      this.showGallary = true
    },
    handleGallaryClose (){
      this.showGallary = false
    }
  },
  components: {
    CommonGallary ,
    FadeAnimation
  }
}
  
</script>

<style scoped>
   .banner{
      position:relative;
       overflow:hidden;
       height:0;
       padding-bottom: 55%   
   }
   .banner-img{ 
      width:100%;
   }
   .banner-info{
     display:flex;
     position:absolute;
     left:0;
     right:0;
     bottom:0;
     line-height:30px;
     color:#fff;
   }
   .banner-title{
     flex:1;
   }
   .banner-number{
     margin-top:7px;
     padding:0 20px;
     height:16px;
     line-height:16px;
     border-radius:10px;
     background:rgba(0, 0, 0, 0.8);
     font-size:12px;
   }
   
</style>