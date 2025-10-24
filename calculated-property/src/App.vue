<script setup>

import Basic from './components/Basic.vue'
import Writable from './components/Writable.vue'

</script>

<template>
  <h1>算出プロパティ</h1>
  <div>
    <div>
      <h2>基本的な例</h2>
      <Basic />
    </div>
    <div>
      <h2>書き込み可能な算出関数</h2>
      <Writable />
    </div>
  </div>
</template>

<style scoped></style>
