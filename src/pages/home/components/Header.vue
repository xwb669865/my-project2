<template>
  <div class="header">
    <div class="header-left">返回</div>
    <div class="header-input">输入城市/景点/游玩主题</div>
    <router-link to='/city'>
      <div class="header-right">  
         {{this.$store.state.city}}
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  
}
</script>

<style  scoped>
   .header{
       display:flex;
       line-height:43px;
       background:#00bcd4;
       color:#fff;

         }
   .header-left{
       width:32px;
       float:left;

   }
   .header-input{
       flex:1;
       height:32px;
       line-height:32px;
       margin-top:6px;
       border-radius:5px;
       background:#fff;
       color:#ccc;
   } 
   .header-right{
       width:62px;
       float:right;
       text-align:center;
       color:#fff;

   }
         
     
</style>