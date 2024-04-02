<template>
    <div>
        <h1>computed</h1>
        <div>{{ fullName }}</div>
    </div>
</template>

<script setup>
import { ref, computed } from 'vue';
const lastName = ref('张');
const firstName = ref('三');
const fullName = computed(() => {
    return lastName.value + firstName.value;
}, {
    immediate: true,
    deep: true
})

setTimeout(() => {
    lastName.value = '李';
    firstName.value = '四';
}, 2000)

</script>

<style scoped lang='scss'></style>