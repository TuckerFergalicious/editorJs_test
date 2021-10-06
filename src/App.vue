<template>
  <div id="app">
    <moodChoice msg="test" />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld";
import moodChoice from "./components/moodChoice";
import mergeTags from "./components/mergeTags";
export default {
  name: "App",
  components: {
    // HelloWorld,
    moodChoice,
    mergeTags,
  },
};
</script>

<style>
/* #app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
