<script setup>
import axios from "axios";
const sendGet = () => axios.get("https://eoj8co2ikh8i0mu.m.pipedream.net");
const sendPost = () =>
  axios.post("https://eoj8co2ikh8i0mu.m.pipedream.net", {
    traQID: "Luftalian",
    grade: 22,
  });
const sendPut = () =>
  axios.put("https://eoj8co2ikh8i0mu.m.pipedream.net", {
    testData: { string: "string", number: 1 },
  });
const sendDelete = () =>
  axios.delete("https://eoj8co2ikh8i0mu.m.pipedream.net", {
    data: { po: 1 },
  });
</script>

<template>
  <div>
    <button @click="sendGet">GET</button>
    <button @click="sendPost">POST</button>
    <button @click="sendPut">PUT</button>
    <button @click="sendDelete">DELETE</button>
  </div>
</template>
