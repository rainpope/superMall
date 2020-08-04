<template>
  <div id="app">
    <top-bar />
    <Nav-Bar />
    <router-view />
    <Footer />

    <tool-bar />
  </div>
</template>

<script>
import TopBar from "components/common/topbar/TopBar";
import NavBar from "components/content/navbar/NavBar";
import Footer from "components/content/footer/Footer";
import ToolBar from "components/content/toolbar/ToolBar";

export default {
  name: "App",
  components: {
    TopBar,
    NavBar,
    Footer,
    ToolBar,
  },
  methods: {},
};
</script>

<style>
@import "assets/css/base.css";
</style>
