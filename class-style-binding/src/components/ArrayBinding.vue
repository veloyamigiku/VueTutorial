<script setup>
import { ref } from 'vue'

const isActive = ref(true)
const activeClass = ref('active')
const errorClass = ref('text-danger')

</script>

<template>
  <div :class="[activeClass, errorClass]">
    Array-Binding(basic)
  </div>
  <div :class="[{[activeClass]: isActive}, errorClass]">
    Array-Binding(object-in-array)
  </div>
</template>
