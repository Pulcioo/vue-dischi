<template>
  <div id="app">
    <HeaderComponent />
    <MainComponent :url="apiUrl" />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
};
</script>

<style lang="scss">
@import "@/style/general";

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: "Montserrat", sans-serif;
}

body {
  background: #1e2d3b;
  width: 100vw;
  height: 100vh;
}
</style>
