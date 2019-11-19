<template>
    <div>
     <div
      class="item"
      v-for="(item, index) of List"
      :key="index"
    >
      <div class="item-title">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :List="item.children"></detail-list>
      </div>
      
    </div>
  </div>

</template>
 
<script>

export default {
  name:'DetailList',
  props: {
      List: Array
  }  
}
  
</script>

<style scoped>
  
  .item-title{
      line-height:40px;
      font-size:16px;
      padding:0 10px;
  } 
  .item-title-icon{
      position:relative;
      left:3px;
      top:3px;
      display:inline-block;
      width:18px;
      height:18px; 
      /* background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -23px no-repeat
       0 -22px no-repeat;  
      margin-right:5px;
      background-size:20px 15px;  */
       background-color:skyblue;
      border-radius:30%; 
  }
  .item-children{
      padding:0 10px;
  } 
</style>