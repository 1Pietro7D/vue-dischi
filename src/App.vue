<template>
  <div id="app">
    <div class="d-flex">
      <AsideNavComp @searchClick="clicker" />
      <div class="d-column">
        <HeaderComp
          :genresList="genres"
          @selectGen="getFilterByGenre"
          :clicked="click"
        />
        <MainComp :cardsList="albumsToDisplay" />
      </div>
    </div>
    <FooterComp />
  </div>
</template>

<script>
import axios from "axios";
import AsideNavComp from "@/components/AsideNavComp.vue";
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import FooterComp from "@/components/FooterComp.vue";

export default {
  name: "App",
  components: {
    AsideNavComp,
    HeaderComp,
    MainComp,
    FooterComp,
  },
  data() {
    return {
      dataUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      cardsAPI: [],
      selectGenre: "",
      click: false,
    };
  },
  created() {
    this.getAlbumData();
  },

  computed: {
    genres() {
      const array = [];
      this.cardsAPI.forEach((item) => {
        if (!array.includes(item.genre)) {
          array.push(item.genre);
        }
      });

      return array;
    },
    albumsToDisplay() {
      const array = [];
      this.cardsAPI.forEach((album) => {
        if (this.hasValidGenre(album)) {
          array.push(album);
        }
      });
      return array;
    },
  },
  methods: {
    getAlbumData() {
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
    getFilterByGenre(genre) {
      console.log("main received", genre);
      this.selectGenre = genre;
    },
    hasValidGenre(album) {
      return this.selectGenre.length === 0 || this.selectGenre === album.genre;
    },
    clicker() {
      if (!this.click) {
        return (this.click = true);
      } else {
        return (this.click = false);
      }
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/style/import.scss";
@import "@/assets/style/generics.scss";
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss";
@import "@/assets/style/flex.scss";
@import "@/assets/style/display.scss";
@import "@/assets/style/grid.scss";
#app {
  height: 100vh;
  @include flex-col;
}
.d-column {
  width: $main-size_w;
}
.container-max {
  max-width: 1200px;
  margin: auto;
  padding: 2rem;
}
</style>

<!--
  @import "@/assets/style/import.scss";
@import "@/assets/style/generics.scss";
@import "@/assets/style/variables.scss";
@import "@/assets/style/position.scss"; 
@import "@/assets/style/flex.scss";
@import "@/assets/style/display.scss";
@import "@/assets/style/grid.scss"; 
-->
