<template>
  <ul>
    VideoList
  </ul>
</template>

<script>
export default {
  name: "VideoList",
  //   props without validation
  //   props: ["videos"]
  //   props with validation (recommended)
  props: {
    videos: Array
  }
};
</script>

<style></style>
