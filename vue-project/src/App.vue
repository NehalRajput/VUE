
<script setup>
const name = "nehal";
const status= 'active';

</script>

<template>
   
   <h1>Hello {{ name }}</h1>
   <p v-if="status === 'active'">user is active</p>
   <p v-else-if="status === 'pending'">user is pending</p>
   <p v-else>user is inactive</p>
   
</template>