<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link 
        tag="li"
        class="item border-bottom" v-for="item of List"
        :key="item.id"
        :to="'/detail/' + item.id"
        >
          <img class="item-img" :src="item.imgUrl" />
          <div class="item-info">
           <p class="item-title">{{item.title}}</p>
           <p class="item-desc">{{item.desc}}</p>
           <button class="item-button">查看详情</button>
          </div>
        
      </router-link>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'HomeRecommend',
  props: {
    List:Array
  }
  /* data (){
    return {
      recommendlist:[
        {
          id:'0001',
          imgUrl:"http://img1.qunarzz.com/sight/p0/1910/1c/1c8f8e8a50115fa6a3.water.jpg_200x200_019b3281.jpg"  ,
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站，浪漫的海洋主题乐园'
        },
        {
          id:'0002',
          imgUrl:"http://img1.qunarzz.com/sight/p0/1910/1c/1c8f8e8a50115fa6a3.water.jpg_200x200_019b3281.jpg"  ,
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站，浪漫的海洋主题乐园'
        },
        {
          id:'0003',
          imgUrl:"http://img1.qunarzz.com/sight/p0/1910/1c/1c8f8e8a50115fa6a3.water.jpg_200x200_019b3281.jpg"  ,
          title:'大连圣亚海洋世界',
          desc:'浪漫大连首站，浪漫的海洋主题乐园'
        }
      ]
    }
    
  
    
  } */
  
}
</script>

<style scoped>
 .title{
   margin-top:10px;
   line-height:40px;
   background:#eee;
   text-indent:10px;

 }
 .item{
   display:flex;
   height:94px;
   
   overflow:hidden;
 }
 .item-img{
   width:85px;
   height:85px;
   padding:5px;              
 }
 .item-info{
   flex:1;
   padding:5px;
   min-width:0;
 }
 .item-title{
   line-height:27px;
   font-size:16px;
 }
 .item-desc{
   line-height:20px;
   color:#ccc;

 }
 .item-button{
   line-height:22px;
   margin-top:8px;
   background:#ff9300;
   padding:0 10px;
   border-radius:3px;
   color:#fff;
 }

</style>