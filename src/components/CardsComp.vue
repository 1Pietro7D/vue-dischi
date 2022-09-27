<template>
  <div class="card">
    <div class="card-img">
      <img :src="url" :alt="genre" />
    </div>
    <h2>{{ title }}</h2>
    <p>{{ author }}</p>
    <p>{{ years }}</p>
  </div>
</template>

<script>
export default {
  name: "CardsComp",

  props: {
    url: String,
    title: String,
    author: String,
    genre: String,
    years: String,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss";
@import "@/assets/style/display.scss";
@import "@/assets/style/flex.scss";
@import "@/assets/style/grid.scss";

.card {
  text-align: center;
  color: $white_theme;
  padding: 1rem;
  .card-img {
    height: calc((100vw - 6rem) / 1 - 2rem);

    @media screen and (min-width: 480px) {
      height: calc((100vw - 6rem) / 2 - 2rem);
    }
    @media screen and (min-width: 780px) {
      height: calc((100vw - 6rem) / 4 - 2rem);
    }
    @media screen and (min-width: 1200px) {
      height: calc(1200px / 5 - 2rem);
    }
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: 0 0;
    }
  }
}
</style>
