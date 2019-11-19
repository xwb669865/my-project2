<template>
 <div class="wrapper">
   <swiper :options="swiperOption" v-if="List.length">
    <swiper-slide v-for="item of List" :key="item.id">
     <img class="swiper-img" :src="item.imgUrl" />
    </swiper-slide>
    
    <div class="swiper-pagination"  slot="pagination"></div>
    
  </swiper>
  </div>
</template>

<script>

export default {
  name: 'HomeSwiper',
  props: {
      List: Array
  },
  data () {
      return {
          swiperOption:{
              pagination:'.swiper-pagination',
              loop:true
          },
          
      }
  },
  
} 
</script>

<style scoped>
   .wrapper{
       width:100%;
       height:0;
       overflow:hidden;
       padding-bottom:31.25%;
       background-color:#eee;
       
   }
   
     
   .swiper-img{
       width:100%
   }
</style>