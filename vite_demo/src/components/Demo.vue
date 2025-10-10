<template>
    <div class="demo">Demo 组件</div>
    <div class="redline">Message : {{ message }}</div>
    <div class="normalline">{{ name }}</div>
    <div class="normalline">{{  obj.message  }}</div>
    <div>reactive: {{  reactive_obj.r_message }}</div>
    <div>toRefs: {{  r_other }}</div>
</template>

<script setup>
    import {ref, reactive, toRefs} from 'vue';
    const message = ref('Hello from Demo component!');
    let name = ref("Vue 3 Data");
    const obj = ref({
        message:"欲穷千里目，更上一层楼。",
    })

    const reactive_obj = reactive({
        r_message:"日日新",
        r_other:"other value"
    })

    let {r_message, r_other} = toRefs(reactive_obj)

    setTimeout(() => {
        console.log("        message")
        message.value = "Message Updated after 2 seconds!"
        obj.value.message = "不畏浮云遮望远，自缘身在最高层。"
        reactive_obj.r_message = reactive_obj.r_message+" 又日新"
        reactive_obj_message.value = "anther value"
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