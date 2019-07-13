<template>
<div class="m-life">
  <el-row>
    <el-col :span="18">
      <slider/>
    </el-col>
    <el-col :span="6">
      <div class="m-life-login">
        <h1><photo/></h1>
        <p class="m-lfe-login-name">Hi!你好</p>
        <p><nuxt-link to="/register"><el-button roudsize="medium">注册</el-button></nuxt-link></p>
        <p><nuxt-link to="/login"><el-button roudsize="medium">立即登录</el-button></nuxt-link></p>
      </div>
    </el-col>
  </el-row>


  <el-row>
    <el-col :span="4">
      <div class="m-life-hotel"/>
    </el-col>
    <el-col :span="4">
      <div class="m-life-music"/>
    </el-col>
    <el-col :span="4">
      <div class="m-life-coop"/>
    </el-col>
    <el-col :span="6">
      <div class="m-life-new"/>
    </el-col>
    <el-col :span="6">
      <div class="m-life-downapp">
        <img src="//s1.meituan.net/bs/fe-web-meituan/60ac9a0/img/download-qr.png" alt="">
        <p>下载客户端</p>
        <h4><span class="red">随时感受</span><em class="gary">音乐的力量</em></h4>
      </div>
    </el-col>
  </el-row>
</div>
</template>

<script>
  import Slider from './slider'
  import Photo from './photo'

  export default {
    components: {
      Slider,
      Photo
    }
  }
</script>
<style lang="scss">
  @import "@/assets/css/index/life.scss";
</style>
