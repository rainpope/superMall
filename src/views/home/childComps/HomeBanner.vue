<template>
  <div id="home-banner">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "HomeBanner",
}
</script>

<style scoped>
#home-banner {
  width: 1226px;
  height: 120px;
  margin: 22px auto;
}
</style>

