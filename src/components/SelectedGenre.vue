<template>
  <div>
    <select @change="showGenre($event)">
      <option value="">All</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Metal">Metal</option>
      <option value="Jazz">Jazz</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectGenre",
  data() {
    return {
      selectGenre: "",
    };
  },
  methods: {
    showGenre(event) {
      console.log(event.target.value);
      this.selectGenre = event.target.value;
      this.$emit("searchByGenre", this.selectGenre);
    },
  },
};
</script>

<style scoped lang="scss">
</style>