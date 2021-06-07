<template>
  <div id="app">
    <SuspenseExample />
  </div>
</template>

<script>
import SuspenseExample from "./components/SuspenseExample.vue";
export default {
  name: "App",
  components: {
    SuspenseExample,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
