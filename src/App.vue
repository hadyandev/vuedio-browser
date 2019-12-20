<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList></VideoList>
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
    }
  }
};
</script>
