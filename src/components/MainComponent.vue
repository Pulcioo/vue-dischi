<template>
  <div class="container">
    <div class="row">
      <div v-if="albums.length > 0" class="col-12">
        <CardAlbum :album="albums[0]" />
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