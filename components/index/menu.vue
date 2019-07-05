<template>
<div class="m-menu">
  <dl class="nav" @mouseleave="mouseleave">
    <dt>全部分类</dt>
    <dd v-for="(item,id) in menu" :key="id" @mouseenter="enter">
      <i :class="item.type"/>{{item.name}} <span class="arrow"/>
    </dd>
    <div class="detail" v-if="kind">
      <template v-for="(item,id) in currentDetail.detail">
        <h4 :key="id">{{item.title}}</h4>
        <span v-for="v in item.child" :key="v">{{ v }}</span>
      </template>
    </div>
  </dl>
</div>
</template>

<script>
export default {
 data(){
   return{
     kind:'',//鼠标当前hover时的类型
     menu:[
       {
       type:'food',
       name:"推荐",
       detail:[{
         title:'美食',
         child:['代金券','甜点饮品','火锅','自助餐','小吃快餐']
       }]
       },
       {
         type:'takeout',
         name:"排行榜",
         detail:[{
           title:'外卖',
           child:['美团外卖']
         }]
       },
       {
         type: 'hotel',
         name: '歌单',
         detail: [{
           title: "酒店星级",
           child: ["经济型", "舒适/三星", "高档/四星", "豪华/五星"]
         }]
       },
       {
         type:'movie',
         name:"主播电台",
         detail:[
           {
           title:'热映电影',
           child:['千与千寻','玩具总动员4','蜘蛛侠']
           },
           {
             title:'热门影院',
             child:['太平洋电影城','万达影城']
           }
         ]
       }, {
         type:'movie',
         name:"歌手",
         detail:[
           {
             title:'热映电影',
             child:['千与千寻','玩具总动员4','蜘蛛侠']
           },
           {
             title:'热门影院',
             child:['太平洋电影城','万达影城']
           }
         ]
       },
       {
         type:'movie',
         name:"新碟上架",
         detail:[
           {
             title:'热映电影',
             child:['千与千寻','玩具总动员4','蜘蛛侠']
           },
           {
             title:'热门影院',
             child:['太平洋电影城','万达影城']
           }
         ]
       },
     ]
   }
 },
  computed:{
    currentDetail(){
      return this.menu.filter((item)=>item.type === this.kind)[0]
    }
  },
  methods:{
   mouseleave(){
     this.kind = ''
   },
    enter(e){
     this.kind = e.target.querySelector('i').className//获取<i/>的className的值
    }

  }
}
</script>

<style scoped>

</style>
