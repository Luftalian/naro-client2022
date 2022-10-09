<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const props = defineProps({
  countryCode: {
    type: String,
    required: true,
  },
});
const countryInfo = ref();
onMounted(async () => {
  const res = await axios.get("/api/countriesss/" + props.countryCode);
  countryInfo.value = res.data;
});
</script>

<template>
  <div>
    <h1>
      <div v-if="countryCode">{{ countryCode }}の街々</div>
      <div v-else>none countryCode</div>
    </h1>
    <div v-if="countryInfo">
      <div v-for="countryInfo in countryInfo" :key="countryInfo.name">
        <router-link :to="`/city/${countryInfo.name}`">
          {{ countryInfo.name }}
        </router-link>
        <router-view />
      </div>
    </div>
    <div v-else>街が見つかりませんでした</div>
  </div>
</template>