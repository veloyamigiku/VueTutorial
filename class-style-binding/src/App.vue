<script setup>
import ArrayBinding from './components/ArrayBinding.vue'
import ObjectBinding from './components/ObjectBinding.vue'
</script>

<template>
  <h1>クラスとスタイルのバインディング</h1>
  <div>
    <h2>オブジェクトへのバインディング</h2>
    <ObjectBinding />
  </div>
  <div>
    <h2>配列へのバインディング</h2>
    <ArrayBinding />
  </div>
  <div>
    <h2>コンポーネントでの使用※ここまで</h2>
  </div>
</template>

<style scoped></style>
