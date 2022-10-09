<script setup>
import axios from "axios";

const logout = () => axios.get("/api/logout");
</script>

<template>
  <div class="logout">
    <h1>This is an logout page</h1>
    <div>
      <button @click="logout">logout</button>
    </div>
  </div>
</template>
