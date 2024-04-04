<script setup lang="ts">
import { ref } from "vue"; // Import ref from Vue


import Post_6 from "./components/Post_6.vue";
import Post_5 from "./components/Post_5.vue";
import Post_4 from "./components/Post_4.vue";
import Post_3 from "./components/Post_3.vue";
import Post_2 from "./components/Post_2.vue";
import Post_1 from "./components/Post_1.vue";

const numPosts = 6; // Number of posts
const showPostIndex = ref(numPosts); // Variable to track which post is shown, initialized to the last post index

const toggleShow = (index: number) => {
  showPostIndex.value = index;
};

// Array of post titles
const postTitles = ref<string[]>([]);
// Populate post titles with template titles
// for (let i = 0; i < numPosts; i++) {
//   postTitles.value.push(`Post ${numPosts - i} title`);
// }
postTitles.value[numPosts - 1] = "Bart's Lawyer is here";
postTitles.value[numPosts - 2] = "A bear sat on it";
postTitles.value[numPosts - 3] = "Right WordPress, you just made the list";
postTitles.value[numPosts - 4] = "How to succeed in gardening without really trying";
postTitles.value[numPosts - 5] = "Why I like watching bike racing on TV";
postTitles.value[numPosts - 6] = "I just have to hope professional complainer is a real job";

</script>

<template>
  <div class="wrapper">
  <div class="header">
    <h1>Blog Day Afternoon</h1>
  </div>

  

  <div class="main">
    <!-- Display the component based on the current post index -->
    <template v-if="showPostIndex === 6">
      <Post_6 />
    </template>
    <template v-else-if="showPostIndex === 5">
      <Post_5 />
    </template>
    <template v-else-if="showPostIndex === 4">
      <Post_4 />
    </template>
    <template v-else-if="showPostIndex === 3">
      <Post_3 />
    </template>
    <template v-else-if="showPostIndex === 2">
      <Post_2 />
    </template>
    <template v-else-if="showPostIndex === 1">
      <Post_1 />
    </template>
    <!-- Add more templates for other posts if needed -->
  </div>

  <div class="sidebar">
    <h3>Recent Posts</h3>
    <br />
    
    <p v-for="(title, index) in postTitles" :key="index">
      <button
        v-if="showPostIndex !== numPosts - index"
        @click="toggleShow(numPosts - index)"
      >
        {{ title }}
      </button>
    </p>
  </div>

  <footer><h1>.....</h1></footer>

  </div>
</template>

<style scoped>
button {
  min-width: 100%;
}

button:hover {
  filter: drop-shadow(0 0 2em #fdfdfdaa);
  background-color: bisque;
  min-width: 100%;
}

button.inactive {
  background-color: rgb(0, 0, 0);
  height: 0px;
  width: 0px;
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