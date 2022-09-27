<template>
  <div id="app">
    <HeaderComp />
    <MainComp :cardsList="cardsAPI" />
    <FooterComp />
  </div>
</template>

<script>
import axios from "axios";
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
  data() {
    return {
      dataUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      cardsAPI: [],
    };
  },
  created() {
    axios
      .get(this.dataUrl)
      .then(({ status, data }) => {
        //uso il destructoring per pensare il valore effettivo richiamando il nome della proprietà,invece di(response) che poi richiama gli elementi con esempio: responde.data

        if (status === 200) {
          this.cardsAPI = data.response;
          console.log(data.response);
        }
      })
      .catch((error) => {
        console.warn(error);
      });
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
