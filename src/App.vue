<template>
  <div id="app">
    <top-bar />
    <Nav-Bar />
    <router-view />
  </div>
</template>

<script>
import TopBar from "components/common/topbar/TopBar";
import NavBar from "components/content/navbar/NavBar";
export default {
  name: "App",
  components: {
    TopBar,
    NavBar,
  },
  methods: {
  },
};
</script>

<style>
@import "assets/css/base.css";
</style>
