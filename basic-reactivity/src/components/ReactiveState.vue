<script>
import { ref } from 'vue'

export default {
  setup() {
    const count = ref(0)

    function increment() {
      count.value++
    }

    return {
      count,
      increment
    }
  }
}
</script>

<template>
  <button @click="increment">
    {{ count }}
  </button>
</template>
