<template>
  <div class="wrap">
    <div class="panel">
      <div class="login" :style="loginStyle">
        <h4>用户登陆</h4>
        <input placeholder="用户名" />
        <input placeholder="密码" type="password" required />
        <button>登录</button>
      </div>
      <div class="trans" :style="transStyle">
        <h4>没有账号？</h4>
        <p>亲爱的快点我去注册吧~</p>
        <button @click="change">注册</button>
      </div>
      <div class="register" :style="regesterStyle">
        <h1>222</h1>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";
let loginStyle = reactive({ width: "340px", opacity: 1 });
let regesterStyle = reactive({ width: "0px", opacity: 0 });
let transStyle = reactive({ "border-radius": "0px 15px 15px 0px" });
function change() {
  if (loginStyle.width == "340px") {
    loginStyle.width = "0px";
    loginStyle.opacity = 0;
    regesterStyle.width = "340px";
    regesterStyle.opacity = 1;
    transStyle["border-radius"] = "15px 0px 0px 15px";
    console.log(transStyle);
  } else {
    loginStyle.width = "340px";
    loginStyle.opacity = 1;
    regesterStyle.width = "0px";
    regesterStyle.opacity = 0;
    transStyle["border-radius"] = "0px 15px 15px 0px";
  }
}
</script>

<style>
@import url("../assets/css/login.css");
</style>
