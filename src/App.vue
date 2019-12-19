<template>
  <div>
    <SearchBar></SearchBar>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";

export default {
  name: "App",
  components: {
    //register the imported component
    SearchBar // SearchBar: SearchBar
  }
};
</script>