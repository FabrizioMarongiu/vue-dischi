<template>
  <div id="app">
    <Header />

    <Main />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
};
</script>

<style lang="scss">
@import "~@fontsource/montserrat/index.css";
@import "~@fontsource/montserrat/700.css";
@import "@/styles/vars";
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: $font;
  font-weight: normal;
  font-size: 16px;
}

#app {
  height: 100vh;
}

.container {
  width: 1200px;
  margin: 0 auto;
}
</style>
