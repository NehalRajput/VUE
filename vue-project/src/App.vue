<script setup>
import { ref } from 'vue'

const tasks = ref([]); 
const newTask = ref(''); 

const addTask = () => {
  if (newTask.value.trim() !== '') {
    tasks.value.push(newTask.value);
  //  console.log('New Task:', newTask.value);
    newTask.value = ''; // Clear input
  } else {
    console.log('Please enter a valid task.');
  }
}
</script>

<template>
  <form @submit.prevent="addTask">
    <label for="newTask">Add a new task:</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" required />
    <button type="submit">Submit</button>

  </form>
  <h1>Tasks</h1>
  <ul>
   <li v-for="task in tasks" >{{ task }}</li>
  </ul>
</template>
