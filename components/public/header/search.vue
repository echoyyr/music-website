<template>
 <div class="search-panel">
   <el-row class="m-header-searchbar">
     <el-col :span="4" class="left">
       <img src="@/assets/logo.png" alt="">
     </el-col>
     <el-col :span="14" class="center">
       <div class="wrapper">
         <el-input
           v-model="search"
           placeholder="音乐/视频/电台/用户"
           @focus="focus()"
           @blur="blur()"
           @input="input()"
         />
         <button class="el-button el-button--primary"><i class="el-icon-search"/></button>
         <dl class="hotPlace" v-if="isHotplace">
           <dt>热门搜索</dt>
           <dd v-for="(item,id) in hotPlace" :key="id">{{item}}</dd>
         </dl>
         <dl class="searchList" v-if="isSearchList">
           <dd v-for="(item,id) in searchList" :key="id">{{item}}</dd>
         </dl>
       </div>
       <p class="suggest">
         <a href="#">一个</a>
         <a href="#">他不喜欢你</a>
         <a href="#">Lights</a>
         <a href="#">改变</a>
       </p>
       <ul class="nav">
         <li>
           <nuxt-link to="/findmusic" class="takeout">发现音乐</nuxt-link>
         </li>
         <li>
           <nuxt-link to="/movie" class="movie">我的音乐</nuxt-link>
         </li>
         <li>
           <nuxt-link to="/hotel" class="hotel">朋友</nuxt-link>
         </li>
         <li>
           <nuxt-link to="/apartment" class="apartment">商城</nuxt-link>
         </li>
         <li>
           <nuxt-link to="/business" class="business">音乐人</nuxt-link>
         </li>
         <li>
           <nuxt-link to="/service">下载客户端</nuxt-link>
         </li>
       </ul>
     </el-col>
     <el-col :span="4" class="right">
       <ul class="security">
         <li><i class="iconfont">&#xe672;</i><p class="txt">会员尊享</p></li>
         <li><i class="iconfont">&#xe6e1;</i><p class="txt">黑胶音质</p></li>
         <li><i class="iconfont">&#xe643;</i><p class="txt">海量下载</p></li>
       </ul>
     </el-col>
   </el-row>
 </div>
</template>

<script>
    export default {
      name: "search",
      data() {
        return {
          search: '',
          isFocus: false,
          hotPlace:['木偶人',"我的名字","晚安","归去来兮"],
          searchList:['reasult1','reasult2','reasult3','reasult4']
        }
      },
      computed: {
        isHotplace: function () {
          return this.isFocus && !this.search
        },
        isSearchList: function () {
          return this.isFocus && this.search
        }
      },
      methods:{
        focus(){
          this.isFocus=true
        },
        blur(){
          this.isFocus=false
          // let self = this;
          // setInterval(function () {
          //   self.isFocus=false
          // },200)
        },
        input(){
          console.log('input')
        }
      }
    }
</script>

<style>

</style>

