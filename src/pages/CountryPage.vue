<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
// const props = defineProps({
//   cityName: {
//     type: String,
//     required: true,
//   },
// });
const countriesInfo = ref();
onMounted(async () => {
  const res = await axios.get("/api/countries");
  countriesInfo.value = res.data;
});
</script>

<template>
  <div>
    <h1>国々</h1>
    <div v-if="countriesInfo">
      <div v-for="countryInfo in countriesInfo" :key="countryInfo.name">
        <router-link :to="`/country/${countryInfo.country}`">
          {{ countryInfo.name }}
        </router-link>
        <router-view />
      </div>
    </div>
    <div v-else>国々が見つかりませんでした</div>
  </div>
</template>
