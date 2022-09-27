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

<style lang="scss" scoped></style>
