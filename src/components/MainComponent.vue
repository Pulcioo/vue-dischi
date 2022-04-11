<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-12">
        <SelectedGenre @searchByGenre="filterByGenre" />
      </div>
      <div
        v-if="albums.length > 0"
        class="col-12 d-flex flex-wrap justify-content-center"
      >
        <CardAlbum
          v-for="(item, index) in filteredList"
          :key="index"
          :album="item"
        />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import CardAlbum from "@/components/CardAlbum.vue";
import SelectedGenre from "@/components/SelectedGenre.vue";

export default {
  name: "MainComponent",
  components: {
    CardAlbum,
    SelectedGenre,
  },
  props: {
    url: String,
  },
  data() {
    return {
      albums: [],
      genre: "",
    };
  },
  mounted() {
    axios.get(this.url).then((response) => {
      this.albums = response.data.response;
      console.log(this.albums[0]);
    });
  },
  computed: {
    filteredList() {
      const filter = this.albums.filter((item) => {
        return item.genre.includes(this.genre);
      });
      return filter;
    },
  },
  methods: {
    filterByGenre(genre) {
      this.genre = genre;
    },
  },
};
</script>

<style scoped lang="scss">
</style>