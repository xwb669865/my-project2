<template>
 <div>
    <router-link
     tag="div"
     to="/" 
     class="header-abs"
     v-show="showAbs"
     >
       <div class="header-abs-back"><</div>
    </router-link>
    <div class="header-fixed"
     v-show="!showAbs"
     :style="opacityStyle"
     >
      <router-link to="/">
       <div class="header-fixed-back"><</div>
      </router-link>
       景点详情
    </div>
 </div>
</template>
 
<script>


export default {
  name:'DetailHeader',
  data () {
      return {
          showAbs: true,
          opacityStyle: {
            opacity:0
          }
      }
  } ,
   methods: {
      handleScroll () {
          const top = document.documentElement.scrollTop
          if(top > 60 && top <140 ){
             let opacity = top / 140
             opacity = opacity > 1 ? 1 : opacity
             this.opacityStyle = { opacity }
             this.showAbs = false
          }else {
             this.showAbs = true
          }
      }
  }, 
    
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  
}
  
</script>

<style scoped>
   .header-abs{
     position:absolute;
     left:10px;
     top:10px;
     width:40px;
     height:40px;
     line-height:40px;
     border-radius:20px;
     text-align:center;
     background:rgba(0,0,0,0.8);
     
   }
   .header-abs-back{
     color:#fff;
     font-size:20px;
     
   }
   .header-fixed{
    z-index: 2;
    position:fixed;
    top:0;
    left:0;
    right:0;
    height:43px;
    line-height:43px;
    text-align:center;
    color:#fff;
    background:green;
    font-size:16px;
    

  }
  .header-fixed-back{
      position:absolute;
      top:0;
      left:0;
      width:32px;
      text-align:center;
      font-size:20px;
      color:#fff;

  }
   
   
</style>