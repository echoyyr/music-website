<template>
  <div class="m-header">
    <el-row>
      <el-col><top-bar></top-bar></el-col>
    </el-row>
    <el-row>
      <el-col><search-bar></search-bar></el-col>
    </el-row>
  </div>
</template>

<script>
  import topBar from './topbar'
  import searchBar from './search'
  export default {
    name: "index",
    components:{
      topBar,
      searchBar
    }
  }
</script>

<style lang="scss">
  @import "@/assets/css/public/header/index.scss";
  @import "@/assets/css/public/layout.scss";
</style>
