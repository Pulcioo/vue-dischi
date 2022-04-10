<template>
  <div id="card" class="text-center m-3">
    <div class="image py-3">
      <img :src="album.poster" :alt="album.title" />
    </div>
    <div class="text p-2">
      <h2 class="mb-3">
        <strong>{{ album.title }}</strong>
      </h2>
      <p class="m-0">{{ album.author }}</p>
      <p>{{ album.year }}</p>
    </div>
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
#card {
  width: 200px;
  background-color: #2c3e50;

  .image {
    width: 100%;

    img {
      width: 70%;
    }
  }

  .text {
    color: grey;

    h2 {
      color: white;
      text-transform: uppercase;
      font-size: large;
    }

    p {
      font-size: medium;
    }
  }
}
</style>
