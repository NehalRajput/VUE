<!-----<script setup>
import { ref, onMounted } from 'vue'

const isLoading = ref(true)
const data = ref([])

onMounted(() => {
  setTimeout(() => {
    data.value = ['Item 1', 'Item 2']
    isLoading.value = false
  }, 2000) 
})
</script>

<template>
  <div v-if="isLoading">
    <p>Loading...</p> 
  </div>
  <ul v-else>
    <li v-for="item in data" :key="item">{{ item }}</li>
  </ul>
</template>
-->


<script setup>
import { ref, onMounted } from 'vue'

const users = ref([])
const isLoading = ref(true)

onMounted(async () => {
  const res = await fetch('https://jsonplaceholder.typicode.com/users')
  users.value = await res.json()
  isLoading.value = false
})
</script>

<template>
  <div v-if="isLoading">Loading users...</div>
  <ul v-else>
    <li v-for="user in users" :key="user.id">{{ user.name }}</li>
  </ul>
</template>
