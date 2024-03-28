<script setup lang="ts">
import { ref } from 'vue'; // Import ref from Vue

import App_2 from './components/App_2.vue';
const show_plan = ref<boolean>(false);

const toggleShowPlan = () => {
  show_plan.value = !show_plan.value;
}


</script>

<template>
  <div class="header">
    <h1>Blog Day Afternoon</h1>
  </div>
  
  <div class="sidebar">
    
    <h3>Recent Posts</h3><br><button @click="toggleShowPlan">How to succeed in gardening without really trying</button></div>
  
  <div  class="main" v-if="show_plan">
    <!-- <h1>App 2 is showing</h1> -->
    <!-- Conditional rendering of App_2 -->
    <App_2  />
  </div>
  <!-- <HelloWorld msg="Vite + Vue from App.vue" />  -->
  
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
