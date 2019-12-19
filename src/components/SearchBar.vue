<template>
  <div>
    <input @input="onInput" />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onInput: function(event) {
      // emitting event to parent component (App)
      this.$emit("termChange", event.target.value);
    }
  }
};
</script>

<style>
</style>