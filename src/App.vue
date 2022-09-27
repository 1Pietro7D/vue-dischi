<template>
  <div>
    <HeaderComp />
    <MainComp />
    <FooterComp />
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import FooterComp from "@/components/FooterComp.vue";

export default {
  name: "App",
  components: {
    HeaderComp,
    MainComp,
    FooterComp,
  },
};
</script>

<style lang="scss">
@import "@/assets/style/import.scss";
</style>

<!--
@import "@/assets/style/generics.scss";
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss"; 
@import "@/assets/style/display.scss";
@import "@/assets/style/flex.scss";
@import "@/assets/style/grid.scss"; 
-->
