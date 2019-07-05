<template>
  <div class="m-nav">
    <ul class="nav">
      <li class="list">
        <nuxt-link to="/my">发现音乐</nuxt-link>
      </li>
      <li class="list">
        <nuxt-link to="/phone-app">我的音乐</nuxt-link>
      </li>
      <li class="list bd">
        <nuxt-link to="/seller-center">朋友</nuxt-link>
      </li>
      <li class="list bd">
        <nuxt-link to="/mt-rule">商城</nuxt-link>
      </li>
      <li class="list site">
        <nuxt-link to="/websites">下载客户端</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: "nav"
  }
</script>

<style>

</style>
