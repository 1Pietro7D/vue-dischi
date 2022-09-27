<template>
  <div>
    <div v-for="(card, index) in info" :key="card[index]">
      {{ card.title }}
    </div>
  </div>
</template>

<script>
export default {
  name: "CardsComp",

  props: {
    info: Array,
  },
};
</script>

<style lang="scss" scoped></style>
