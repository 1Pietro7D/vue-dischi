<template>
  <div class="card-container">
    <div class="card">
      <div class="card-img">
        <img :src="url" :alt="genre" @error="replaceUrl" />
      </div>
      <h3>{{ title }}</h3>
      <span>{{ author }} </span>
      <span> ({{ year }})</span>
    </div>
  </div>
</template>

<script>
import bonjovi from "@/assets/img/th.png";
export default {
  name: "CardsComp",

  props: {
    url: String,
    title: String,
    author: String,
    genre: String,
    year: String,
  },
  methods: {
    replaceUrl(e) {
      if (this.author === "Bon Jovi" && this.title === "New Jersey") {
        e.target.src = bonjovi;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";

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
      height: calc($main_size_w - 10rem);

      width: calc($main_size_w - 10rem);
      @media screen and (min-width: calc(480px + $asideNav_size_w )) {
        height: calc(($main_size_w - 6rem) / 2 - 4rem);
        width: calc(($main_size_w - 6rem) / 2 - 4rem);
      }
      @media screen and (min-width: calc(780px + $asideNav_size_w )) {
        height: calc(($main_size_w - 6rem) / 3 - 4rem);
        width: calc(($main_size_w - 6rem) / 3 - 4rem);
      }
      @media screen and (min-width: calc(1000px + $asideNav_size_w )) {
        height: calc(($main_size_w - 6rem) / 4 - 4rem);
        width: calc(($main_size_w - 6rem) / 4 - 4rem);
      }
      @media screen and (min-width: calc(1200px + $asideNav_size_w )) {
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
