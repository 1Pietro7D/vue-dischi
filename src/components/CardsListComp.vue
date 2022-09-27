<template>
  <div>
    <CardsComp :info="cards" />
  </div>
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

<style lang="scss" scoped></style>
