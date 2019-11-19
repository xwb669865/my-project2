<template>
  <div class="icons">
   <swiper >
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div
          class="icon"
          v-for="item of page"
          :key="item.id"
        >
          <div class='icon-img'>
            <img class='icon-img-content' :src='item.imgUrl' />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
     
    </swiper>
    
    
  </div>
</template>

<script>

export default {
  name: 'HomeIcons',
  props: {
    List: Array
  },
   
  computed: {
    pages (){
      const pages = []
      this.List.forEach((item,index) => {
        const page = Math.floor(index / 8)
        if(!pages[page]){
           pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
   
  
  
} 

</script>

<style  scoped>
  .icons >>> .swiper-container{
    
    height:0;
    padding-bottom:50%;
    
  }
  .icon{
    position:relative;
    overflow:hidden;
    float:left;
    height:0;
    width:25%;
    padding-bottom:25%;
    
  }
  .icon-img{
    
    position:absolute;
    width:80%;
    top:0;
    left:0;
    right:0;
    bottom:22px;
    box-sizing:border-box;
    padding:5px;
    
  }
  .icon-img-content{
    width:100%;
    
    
    display:block;
    margin:0 auto;
    height:100%;
  }
  .icon-desc{
    position:absolute;
    
    left:-24px;/* 0 */
    right:0;
    bottom:0;
    height:22px;
    line-height:22px;
    color:#333;
    text-align:center;
  } 
</style>