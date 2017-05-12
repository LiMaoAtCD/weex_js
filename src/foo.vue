<template>
  <div class="wrapper" @click="update">
    <image :src="logoUrl" class="logo"></image>
    <text class="title">Hello {{target}}</text>
    <text class="baseInfo"> {{ UserInfo }}</text>
  </div>

</template>

<style>
  .wrapper { align-items: center; margin-top: 120px; }
  .title { font-size: 48px; }
  .logo { width: 360px; height: 82px; }

  .baseInfo {
    font-size: 48px;
  }
</style>

<script>
  export default {
    data: {
      logoUrl: 'https://alibaba.github.io/weex/img/weex_logo_blue@3x.png',
      target: 'World',
      UserInfo: "userInfo"
    },
    methods: {
      update: function (e) {
        this.target = 'Weex'
        console.log('target:', this.target)

         var baseModule = require('@weex-module/userinfo'); 
         this.UserInfo = baseModule.getUserInfo();
        console.log('baseModule get user info'+ this.UserInfo);
      }
    }
  }

 

</script>
