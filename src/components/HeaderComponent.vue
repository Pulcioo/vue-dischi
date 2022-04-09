<template>
  <div id="header-container" class="container-fluid w-100">
    <img src="../assets/spotify-logo.png" alt="Logo" />
  </div>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style scoped lang="scss">
#header-container {
  background-color: #2c3e50;

  img {
    width: 50px;
    margin: 10px 0;
  }
}
</style>