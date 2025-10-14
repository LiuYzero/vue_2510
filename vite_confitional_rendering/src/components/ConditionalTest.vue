<template>
    <hr/>
    <div v-text="message"></div>
    <hr/>
    <div v-html="html_message"></div>
    <hr/>
    <p>username: <input type="text" v-bind:placeholder="username"></p>
    <p>password: <input type="password" v-bind:placeholder="password"></p>
    <hr/>
    <p>username: {{ username }}</p>
    <button v-on:click="buttonClickedFunc">Click Me For username changed</button>
    <hr/>
    <p>数据双向绑定</p>
    Input username: <input type="text" v-model.lazy="your_username"><br/>
    Your name is {{ your_username }}<br/>
    <hr/>
    <p>数据双向绑定的加法计算</p>
    <p>输入第一个数字: <input type="number" v-model.number="firstNumber"></p>
    <p>输入第二个数字: <input type="number" v-model.number="secondNumber"></p>
    <p>结果: {{ firstNumber + secondNumber }}</p>
    <hr/>
</template>

<script setup>
    import { ref } from "vue"
    const message = "<span>这里是v-text指令的使用</span>, First Time"
    const html_message = "<strong>这里是v-html指令的使用 strong line</strong>"
    let username = ref("请输入用户名")
    const password = ref("请输入密码")
    const buttonClickedFunc = () => {
        username.value = "new username"
    }

    const your_username = ref("")
    const firstNumber = ref(0)
    const secondNumber = ref(0) 
</script>

export default {
    name: "ConditionalTest"
}
