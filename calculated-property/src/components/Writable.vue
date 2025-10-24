<script setup>
import { computed, ref } from 'vue'

const firstName = ref('')
const lastName = ref('')

const fullName = computed({
  get() {
    console.log('Getter called')
    if (firstName.value == '' && lastName.value == '') {
      return ''
    } else {
      if (firstName.value !== '' && lastName.value === '') {
        return firstName.value
      } else {
        return firstName.value + ' ' + lastName.value
      }
    }
  },
  set(value) {
    console.log('Setter called')
    const names = value.split(' ')
    if (names.length >= 2) {
      firstName.value = names[0]
      lastName.value = names[1]
    } else if (names.length === 1) {
      firstName.value = names[0]
      lastName.value = ''
    } else {
      firstName.value = ''
      lastName.value = ''
    }
  }
})
</script>

<template>
  <div>
    <p>名字:{{ lastName }}</p>
    <p>フルネーム:{{ fullName }}</p>
    <input v-model="lastName" placeholder="Enter your last name" />
    <input v-model="fullName" placeholder="Enter your full name" />
  </div>
</template>
