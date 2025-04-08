
<script setup>
import { ref } from 'vue'

const name = "nehal";
const status= 'active';
const colors = ref(['Red', 'Green', 'Blue']);
const link = 'https://www.google.com/';

const count = ref(0)

function increment() {
  count.value++
}
</script>

<template>
   
   <h1>Hello {{ name }}</h1>
   <p v-if="status === 'active'">user is active</p>
   <p v-else-if="status === 'pending'">user is pending</p>
   <p v-else>user is inactive</p>

   <ul>
      <li v-for="color in colors">{{ color }}</li>
   </ul>
   <a v-bind:href="link">click for google</a>
   
   <h1>Count: {{ count }}</h1>
   <button @click="increment">Increment</button>

</template>
