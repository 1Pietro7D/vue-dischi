<template>
  <section class="container-max my-grid">
    <CardsComp
      v-for="(card, index) in cards"
      :key="card[index]"
      :url="cards[index].poster"
      :title="cards[index].title"
      :author="cards[index].author"
      :year="cards[index].year"
    />
  </section>
</template>

<script>
import CardsComp from "@/components/CardsComp.vue";
export default {
  name: "CardsListComp",
  components: { CardsComp },
  props: {
    cards: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss";
@import "@/assets/style/display.scss";
@import "@/assets/style/flex.scss";
@import "@/assets/style/grid.scss";
section {
  &.my-grid {
    @include grid-comp-col-1;

    @media screen and (min-width: calc(480px + $asideNav_size_w)) {
      @include grid-comp-col-2;
    }
    @media screen and (min-width: calc(780px + $asideNav_size_w)) {
      @include grid-comp-col-3;
    }
    @media screen and (min-width: calc(1000px + $asideNav_size_w)) {
      @include grid-comp-col-4;
    }
    @media screen and (min-width: calc(1200px + $asideNav_size_w)) {
      @include grid-col-5;
    }
    @media screen and (max-width: (1200px + $asideNav_size_w)) {
      padding: 2rem $padding_x_my_grid;
    }
  }
}
</style>
