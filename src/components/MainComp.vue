<template>
  <main>
    <CardsListComp :cards="cardsList" />
  </main>
</template>

<script>
import CardsListComp from "@/components/CardsListComp.vue";
export default {
  name: "MainComp",
  components: {
    CardsListComp,
  },
  props: {
    cardsList: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
main {
  background-color: $main_theme;
  height: $main_size_h;

  overflow-y: scroll;
}
</style>
