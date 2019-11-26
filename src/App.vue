<template>
  <div id="app">
    <Kanye/>
  </div>
</template>

<script>
import Kanye from "./components/Kanye";

export default {
  name: "App",
  components: {
    Kanye
  }
};
</script>

<style>
body,
html {
  padding: 0;
  margin: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
