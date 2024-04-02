<template>
  <div class="app">
    <div class="item">
      <reactiveAndRef />
    </div>
    <div class="item">
      <refAndtoRef />
    </div>
    <div class="item">
      <computedE />
    </div>
    <div class="item">
      <watchE />
    </div>
  </div>
</template>

<script setup>
import computedE from './components/computedE.vue'
import watchE from './components/watchE.vue'
import reactiveAndRef from './components/01.reactiveAndRef.vue'
import refAndtoRef from './components/02.refAndtoRef.vue'
</script>

<style lang="scss">
.app {
  width: 100%;

  .item {
    width: 100%;
    border-top: 1px dashed #000;
    margin: 10px 0;
  }
}
</style>
