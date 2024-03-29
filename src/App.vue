<script setup lang="ts">
import { ref } from "vue"; // Import ref from Vue

import App_2 from "./components/App_2.vue";

import App_3 from "./components/App_3.vue";

const showPosts = ref<boolean[]>([true, false, false]); // Array to track which posts are shown


const toggleShow = (index: number) => {
  showPosts.value = showPosts.value.map((_, i) => i === index);
  
};
</script>

<template>
  <div class="header">
    <h1>Blog Day Afternoon</h1>
  </div>

  <div class="sidebar">
    <h3>Recent Posts</h3>
    <br />

    <p>
      <button @click="toggleShow(1)" v-if="!showPosts[1]">
        How to succeed in gardening without really trying
      </button>
    </p>
    <p>
      <button @click="toggleShow(2)">
        Right WordPress, you just made the list
      </button>
    </p>
    <p>
      <button @click="toggleShow(3)">A bear sat on it</button>
    </p>
    <p>
      <button @click="toggleShow(4)">Bart's lawyer is here</button>
    </p>
  </div>

  <div class="main" v-if="showPosts[0]">
    <App_2 />
  </div>
  <div class="main" v-if="showPosts[1]">
    <App_3 />
  </div>
   <div class="main" v-if="showPosts[2]">
    <App_2 />
  </div>
  <!-- <HelloWorld msg="Vite + Vue from App.vue" />  -->
</template>

<style scoped>
button {
  min-width: 100%;
}

button:hover {
  filter: drop-shadow(0 0 2em #fdfdfdaa);
  background-color: bisque;
}
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
