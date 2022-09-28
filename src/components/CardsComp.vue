<template>
  <div class="card-container">
    <div class="card">
      <div class="card-img">
        <img :src="url" :alt="genre" />
      </div>
      <h3>{{ title }}</h3>
      <span>{{ author }} </span>
      <span> ({{ year }})</span>
    </div>
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
    year: String,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss";
@import "@/assets/style/display.scss";
@import "@/assets/style/flex.scss";
@import "@/assets/style/grid.scss";
.card-container {
  font-size: medium;
  padding: 0 1rem;
  margin-bottom: 2rem;
  .card {
    text-align: center;
    color: $white_theme;
    padding: 1rem;
    background-color: $card_theme;
    height: 100%;

    .card-img {
      margin-bottom: 1.5rem;
      height: calc((100vw - 6rem) / 1 - 4rem);
      width: calc((100vw - 6rem) / 1 - 4rem);
      @media screen and (min-width: 480px) {
        height: calc((100vw - 6rem) / 2 - 4rem);
        width: calc((100vw - 6rem) / 2 - 4rem);
      }
      @media screen and (min-width: 780px) {
        height: calc((100vw - 6rem) / 3 - 4rem);
        width: calc((100vw - 6rem) / 3 - 4rem);
      }
      @media screen and (min-width: 1000px) {
        height: calc((100vw - 6rem) / 4 - 4rem);
        width: calc((100vw - 6rem) / 4 - 4rem);
      }
      @media screen and (min-width: 1200px) {
        height: calc((1200px - 4rem) / 5 - 4rem);
        width: calc((1200px - 4rem) / 5 - 4rem);
      }
      img {
        height: 100%;
        width: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
