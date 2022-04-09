<template>
  <div id="card">
    <img :src="album.poster" :alt="album.title" />
    <h2>{{ album.title }}</h2>
    <p>{{ album.author }}</p>
    <p>{{ album.year }}</p>
  </div>
</template>

<script>
export default {
  name: "CardAlbum",
  props: {
    album: Object,
  },
};
</script>

<style scoped lang="scss">
</style>
