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
         title:'全部分类',
         child:['语种','风格','场景','情感','主题']
       }]
       },
       {
         type:'takeout',
         name:"排行榜",
         detail:[{
           title:'云音乐特色榜',
           child:['云音乐飙升榜']
         }]
       },
       {
         type: 'hotel',
         name: '歌单',
         detail: [{
           title: "全部分类",
           child: ['语种','风格','场景','情感','主题']
         }]
       },
       {
         type:'movie',
         name:"主播电台",
         detail:[
           {
           title:'推荐节目',
           child:['创作/翻唱','3D|电子','情感调频']
           },
           {
             title:'节目排行榜',
             child:['外语世界','亲子宝贝']
           }
         ]
       }, {
         type:'singer',
         name:"歌手",
         detail:[
           {
             title:'入驻歌手',
             child:['张惠妹','Fine乐团','洪启']
           },
           {
             title:'热门歌手',
             child:['薛之谦','花粥']
           }
         ]
       },
       {
         type:'xindie',
         name:"新碟上架",
         detail:[
           {
             title:'热门新碟',
             child:['忘记拥抱','光之海','BTS']
           },
           {
             title:'全部新碟',
             child:['JUST','MOSHI']
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
