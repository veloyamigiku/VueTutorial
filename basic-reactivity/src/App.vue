<script>
import Reactive from './components/Reactive.vue'
import ReactiveState from './components/ReactiveState.vue'
import ReactiveStateSFC from './components/ReactiveStateSFC.vue'

export default {
  components: {
    Reactive,
    ReactiveState,
    ReactiveStateSFC
  }
}
</script>

<template>
  <h1>リアクティビティーの基礎</h1>
  <div>
    <h2>リアクティブな状態を宣言する</h2>
    <ReactiveState />
  </div>
  <div>
    <h2>script setup</h2>
    <ReactiveStateSFC />
  </div>
  <div>
    <h2>reactive()</h2>
    <Reactive />
  </div>
  <div>
    <h2></h2>
  </div>
</template>

<style scoped></style>
