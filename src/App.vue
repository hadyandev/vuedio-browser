<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList @videoSelect="onVideoSelect" :videos="videos"></VideoList>
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
const API_KEY = "AIzaSyB0ToJFPdt3Dp2stb8ynXqHkNe9U0ivB0c";

export default {
  name: "App",
  components: {
    //register the imported component
    SearchBar, // SearchBar: SearchBar
    VideoList
  },
  // data property on vue component MUST be a function
  data() {
    return {
      videos: []
    };
  },
  methods: {
    // searchTerm adalah value yg didapat dari search bar (event.target.value yang didefinisikan di SearchBar component)
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(response => {
          // update videos property with data from api
          this.videos = response.data.items;
        });
    },

    onVideoSelect(video) {
      console.log(video);
    }
  }
};
</script>
