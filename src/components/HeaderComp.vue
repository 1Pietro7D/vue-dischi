<template>
  <header>
    <div class="logoContainer">
      <img src="@/assets/img/logo-small.svg" alt="" />
    </div>
    <select name="" id="" v-model="userChoice" @change="onChange">
      <option v-for="option in genresList" :key="option" :value="option">
        {{ option }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
  props: {
    genresList: Array,
  },
  data() {
    return { userChoice: "" };
  },
  methods: {
    onChange() {
      this.$emit("selectGenre", this.userChoise);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
@import "@/assets/style/flex.scss";

header {
  background-color: $header_theme;
  height: $header-size_h;
  display: flex;
  align-items: center;
  gap: 3rem;
  padding: 0 2rem;
  .logoContainer {
    margin-left: 1rem;
    $size: 50px;
    height: $size;
    width: $size;
    img {
      width: $size;
      height: $size;
      object-fit: scale-down;
    }
  }
}
</style>
