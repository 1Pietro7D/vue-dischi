<template>
  <header>
    <div class="logoContainer">
      <img src="@/assets/img/logo-small.svg" alt="" />
    </div>
    <select
      name=""
      class="d-none"
      id=""
      v-model="userChoice"
      @change="onChange"
      :class="{ active: clicked === true }"
    >
      <option value="">Nessuno selezionato</option>
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
    clicked: Boolean,
  },
  data() {
    return {
      userChoice: "",
    };
  },
  methods: {
    onChange() {
      console.log(this.userChoice);
      this.$emit("selectGen", this.userChoice);
    },
    onClick() {
      this.$emit("status", this.clicked);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";

header {
  background-color: $header_theme;
  height: $header-size_h;
  display: flex;
  align-items: center;
  gap: 3rem;
  padding: 0 2rem;
  .active {
    display: inline-block;
  }
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
