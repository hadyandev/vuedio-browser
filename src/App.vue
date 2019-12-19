<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";

export default {
  name: "App",
  components: {
    //register the imported component
    SearchBar // SearchBar: SearchBar
  },
  methods: {
    onTermChange: function(searchTerm) {
      alert(searchTerm);
    }
  }
};
</script>