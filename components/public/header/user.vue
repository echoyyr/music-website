<template>
  <div class="m-user">
    <template v-if="user">
      欢迎您！<span class="username">{{user}}</span>
      <nuxt-link to="/exit">退出</nuxt-link>
    </template>

    <template v-else>
      <div class="log">
      <nuxt-link to="/login" class="login">立即登录</nuxt-link>
      <nuxt-link to="register" class="register">注册</nuxt-link>
      </div>
    </template>

  </div>

</template>

<script>
  export default {
    name: "user",
    data(){
      return{
        user:''
      }
    }
  }
</script>

<style scoped>

</style>

