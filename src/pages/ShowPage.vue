<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
// const props = defineProps({
//   cityName: {
//     type: String,
//     required: true,
//   },
// });
const contextsInfo = ref();
onMounted(async () => {
  const res = await axios.get("/api/show");
  contextsInfo.value = res.data;
});
</script>

<template>
  <div>
    <h1>投稿一覧</h1>
    <div v-if="contextsInfo">
      <div v-for="contextInfo in contextsInfo" :key="contextInfo">
        {{ contextInfo }}
      </div>
    </div>
    <div v-else>投稿が見つかりませんでした</div>
  </div>
</template>
