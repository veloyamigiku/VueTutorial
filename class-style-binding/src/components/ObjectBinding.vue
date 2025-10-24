<script setup>
import { computed, reactive, ref } from 'vue'

const isActive = ref(true)
const hasError = ref(false)
const error = ref(null)

const classObject = reactive({
  active: true,
  'text-danger': false
})

const classObjectComputed = computed(() => ({
  active: isActive.value && !error.value,
  'text-danger': error.value && error.value.type === 'fatal'
}))

</script>

<template>
  <div
    class="static"
    :class="{active: isActive, 'text-danger': hasError}">
    Object-Binding(inline)
  </div>
  <div :class="classObject">Object-Binding(not-inline)</div>
  <div :class="classObjectComputed">Object-Binding(computed)</div>
</template>