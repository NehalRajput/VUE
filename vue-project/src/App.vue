<script setup>
import { ref, watch } from 'vue'

const name = ref('')
const message = ref('')

watch(name, (newVal, oldVal) => {
  if (newVal.length > 0) {
    message.value = `Hello, ${newVal}!`
  } else {
    message.value = ''
  }
})
</script>

<template>
  <input v-model="name" placeholder="Enter your name" />
  <p>{{ message }}</p>
</template>
