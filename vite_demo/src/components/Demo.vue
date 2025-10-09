<template>
    <div class="demo">Demo 组件</div>
    <div class="redline">Message : {{ message }}</div>
    <div class="normalline">{{ name }}</div>
    <div class="normalline">{{  obj.message  }}</div>
</template>

<script setup>
    import {ref} from 'vue';
    const message = ref('Hello from Demo component!');
    let name = ref("Vue 3 Data");
    const obj = ref({
        message:"欲穷千里目，更上一层楼。",
    })

    setTimeout(() => {
        console.log("before message")
        message.value = "Message Updated after 2 seconds!"
        obj.value.message = "不畏浮云遮望远，自缘身在最高层。"
        console.log("message")
    }, 2000);
</script>


<style>
.demo {
    font-size: 22px;
    font-weight: bold;
}
.redline {
    color: red;
}
.normalline{
    color: black;
    font-size: 12px;
}
</style>

export default {
    name: 'Demo';
}