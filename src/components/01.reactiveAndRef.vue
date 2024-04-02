<template>
    <div>
        <h1>01. reactiveAndRef</h1>
        <h2>---- reactive ----</h2>
        <div>{{ obj }}</div>
        <h2>---- ref ----</h2>
        <div>{{ obj2 }}</div>
    </div>
</template>

<script setup>
console.log('↓↓↓↓↓↓↓↓↓↓↓ 01. reactiveAndRef ↓↓↓↓↓↓↓↓↓↓↓');
import { ref, reactive } from 'vue';
// reactive只能代理对象，不能代理基本数据类型。直接使用Proxy进行代理，不需要额外包装。
// ref可以代理基本数据类型，也可以代理对象。Vue会将数据进行包装。

// 总结和用法
// 作者：白瑞德
// 链接：https://juejin.cn/post/7211055301205934138
//   1. ref可以存储原始类型，而reactive不能。
//   2. ref需要通过<ref>.value访问数据，而reactive()可以直接用作常规对象。
//   3. 可以重新分配一个全新的对象给ref的value属性，而reactive()不能。
//   4. ref类型为Ref<T>，而reactive返回的反应类型为原始类型本身。
//   5. 基于第四条，ref可以自身管理依赖而reactive则借助全局变量以键值对的形式进行管理。
//   6. watch默认只观察ref的value，而对reactive则执行深度监听。
//   7. ref默认会用reactive 对象类型的原始值进行深层响应转换。
const obj = reactive({
    name: '张三',
    age: 18
})

const obj2 = ref({
    name: '李四',
    age: 19
})
console.log(obj, obj2); // Proxy  RefImpl
console.log(obj.name, obj2.value.name); // 张三 李四
</script>

<style scoped lang='scss'></style>