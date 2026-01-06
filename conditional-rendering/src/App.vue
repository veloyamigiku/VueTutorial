<script setup>
import { ref } from 'vue'
const awesome = ref(true)
const type = ref("A")
const ok = ref(true)
</script>

<template v-if>
  <div>
    <h1>v-if</h1>
    <h3 v-if="awesome">Vue is awesome!</h3>
  </div>
  <div>
    <h1>v-else</h1>
    <button @click="awesome = !awesome">Toggle</button>
    <h3 v-if="awesome">Vue is awesome!</h3>
    <h3 v-else>Oh no 😢</h3>
  </div>
  <div>
    <h1>v-else-if</h1>
    <div v-if="type === 'A'">A</div>
    <div v-else-if="type === 'B'">B</div>
    <div v-else-if="type === 'C'">C</div>
    <div v-else>Not A/B/C</div>
  </div>
  <div>
    <h1>&lt;template&gt;にv-ifを適用する</h1>
    <template v-if="ok">
      <h1>Title</h1>
      <p>Paragraph 1</p>
      <p>Paragraph 2</p>
    </template>
  </div>
  <div>
    <h1>v-show</h1>
    <h3 v-show="ok">Hello!</h3>
  </div>
</template>

<style scoped></style>
