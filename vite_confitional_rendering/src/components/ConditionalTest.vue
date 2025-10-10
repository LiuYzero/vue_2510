<template>
    <hr/>
    <div v-text="message"></div>
    <hr/>
    <div v-html="html_message"></div>
    <hr/>
    <p>username: <input type="text" v-bind:placeholder="username"></p>
    <p>password: <input type="password" v-bind:placeholder="password"></p>
    <hr/>
</template>

<script setup>
    const message = "<span>这里是v-text指令的使用</span>, First Time"
    const html_message = "<strong>这里是v-html指令的使用 strong line</strong>"
    const username = "请输入用户名"
    const password = "请输入密码"
</script>

export default {
    name: "ConditionalTest"
}
