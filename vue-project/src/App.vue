<script setup>
import { ref, computed } from 'vue'

const num1 = ref(10)
const num2 = ref(20)

const sum = computed(() => num1.value + num2.value)
</script>

<template>
  <p>Number 1: {{ num1 }}</p>
  <p>Number 2: {{ num2 }}</p>
  <p>Sum: {{ sum }}</p>
</template>
