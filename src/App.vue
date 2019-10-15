<template>
  <div id="app">
    <DynamicGrid/>
  </div>
</template>

<script>
import DynamicGrid from "./components/DynamicGrid";

export default {
  name: "App",
  components: {
    DynamicGrid
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
