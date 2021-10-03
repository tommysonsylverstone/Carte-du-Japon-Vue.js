<template>
  <JapanMap />
</template>

<script>
import JapanMap from "../components/JapanMap.vue";
export default {
  name: "App",
  components: {
    JapanMap,
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  padding:0;
  margin:0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>