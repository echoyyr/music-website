<template>
  <el-row class="m-header" :gutter="0">
    <el-col :span="5"><geo></geo></el-col>
    <el-col :span="5"><user></user></el-col>
    <el-col :span="14"><navbar></navbar></el-col>
  </el-row>
</template>

<script>
  import Geo from './geo'
  import User from './user'
  import Navbar from './nav'
  export default {
    name: "index",
    components:{
      Geo,
      User,
      Navbar
    }
  }
</script>

<style lang="scss">


</style>
