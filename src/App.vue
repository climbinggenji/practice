<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import "@/assets/css/scroll.css"
export default {
  name: "App"
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
}
div {
  box-sizing: border-box;
}
html,
body {
  height: 100%;
}
#app {
  width: 1050px;
  margin: 0 auto;
  /* box-shadow: 0 0 5px #7f7f7f; */
}
</style>
