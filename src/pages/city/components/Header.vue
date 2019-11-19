<template>
 <div class="header">
     城市选择
     <router-link to="/">
      <div class="header-back"><</div>
     </router-link>
 </div>
</template>

<script>


export default {
  name:'CityHeader',
  



}
  
</script>

<style scoped>
  .header{
    position:relative;
    overflow:hidden;
    height:43px;
    line-height:43px;
    text-align:center;
    color:#fff;
    background:green;
    font-size:16px;
    

  }
  .header-back{
      position:absolute;
      top:0;
      left:0;
      width:32px;
      text-align:center;
      font-size:20px;
      color:#fff;

  }
</style>