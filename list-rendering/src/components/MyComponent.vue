<script setup>
defineProps(['item'])
</script>

<template>
  <div>
    <h3>{{ item.message1 }} - {{ item.message2 }} - {{ item.message3 }}</h3>
  </div>
</template>
