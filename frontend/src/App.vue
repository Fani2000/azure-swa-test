<script setup lang="ts">
import { onMounted, ref } from "vue";
// import HelloWorld from './components/HelloWorld.vue'
import axios from "axios";
// import { VideoPlayer } from "@videojs-player/vue";

const message = ref("");

onMounted(async () => {
  const res = await axios.get("api/getDetails");
  message.value = res.data;
});

// const option = { src: "rtsp://88.159.118.92:9000/live", type: "video/rtsp" };

// document.addEventListener("DOMContentLoaded", function () {
//   const video = document.getElementById("video");
//   const hlsUrl = "http://127.0.0.1:8000/output.m3u8";

//   if (Hls.isSupported()) {
//     const hls = new Hls();
//     hls.loadSource(hlsUrl);
//     hls.attachMedia(video);
//     hls.on(Hls.Events.MANIFEST_PARSED, function () {
//       video.play();
//     });
//   } else if (video.canPlayType("application/vnd.apple.mpegurl")) {
//     video.src = hlsUrl;
//     video.addEventListener("loadedmetadata", function () {
//       video.play();
//     });
//   } else {
//     console.error("HLS is not supported in this browser");
//   }
// });
</script>

<template>
  <div>
    <div>Welcome {{ message }}</div>
    <!-- <video-player :sources="[option]" controls :volume="0.6" autoplay /> -->
    <!-- <video id="video" width="640" height="360" controls></video> -->
  </div>
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
