<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <PageCounter msg="Voxy word counter" />
</template>

<script>
import PageCounter from "./components/PageContents.vue";

export default {
  name: "App",
  components: {
    PageCounter,
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
