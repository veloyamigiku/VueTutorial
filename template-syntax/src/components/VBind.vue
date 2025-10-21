<script>
import { ref } from 'vue';

export default {
  setup() {
    const dynamicId1 = ref("id1")
    const dynamicId2 = ref("id2")
    const id = ref("id3")

    return {
      dynamicId1,
      dynamicId2,
      id
    }
  }
}
</script>

<template>
  <div>
    <div v-bind:id="dynamicId1"></div>
    <!-- v-bindの値がnullの場合は、属性がレンダリングされない -->
    <div v-bind:id="null"></div>
    <div :id="dynamicId2"></div>
    <div :id></div>
  </div>
</template>