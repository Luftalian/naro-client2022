<script setup>
import axios from "axios";
import { ref } from "vue";

const contexts = ref("");
const write = () =>
  axios.post("/api/write", {
    username: "",
    contexts: contexts.value,
  });
</script>

<template>
  <div class="write">
    <h1>This is a write page</h1>
    <div>
      <input type="text" v-model="contexts" />
    </div>
    <div>
      <button @click="write">投稿する</button>
    </div>
  </div>
</template>
