<template>
  <ul>
    <VideoListItem></VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";

export default {
  name: "VideoList",
  components: {
    VideoListItem
  },
  //   props without validation
  //   props: ["videos"]
  //   props with validation (recommended)
  props: {
    videos: Array
  }
};
</script>

<style></style>
