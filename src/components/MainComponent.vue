<template>
  <div class="container py-5">
    <div class="row">
      <div
        v-if="albums.length > 0"
        class="col-12 d-flex flex-wrap justify-content-center m"
      >
        <CardAlbum v-for="(item, index) in albums" :key="index" :album="item" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import CardAlbum from "@/components/CardAlbum.vue";

export default {
  name: "MainComponent",
  components: {
    CardAlbum,
  },
  props: {
    url: String,
  },
  data() {
    return {
      albums: [],
    };
  },
  mounted() {
    axios.get(this.url).then((response) => {
      this.albums = response.data.response;
      console.log(this.albums[0]);
    });
  },
};
</script>

<style scoped lang="scss">
</style>