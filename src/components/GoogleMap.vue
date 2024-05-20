<template>

  <iframe width="100%" height="250" style="border: 0" loading="lazy" allowfullscreen
    referrerpolicy="no-referrer-when-downgrade" :src="`${baseUrl}?key=${key}&q=${encodeURIComponent(props.query)}`">
  </iframe>

</template>

<script setup lang="ts">
const baseUrl = "https://www.google.com/maps/embed/v1/place";
const key = "AIzaSyCZgPdOvKYfGs-7xau3Q-uFt0cMRHJ_hzQ";

const props = defineProps({
  query: { type: String, default: () => "" }
})
</script>

<style scoped></style>
