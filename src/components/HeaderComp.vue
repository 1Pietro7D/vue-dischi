<template>
  <header>
    <div class="logoContainer">
      <img src="@/assets/img/logo-small.svg" alt="" />
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
header {
  padding: 1.5rem;
  background-color: $header_theme;
  .logoContainer {
    margin-left: 1rem;
    $size: 75px;
    height: $size;
    width: $size;
    img {
      width: $size;
      height: $size;
      object-fit: scale-down;
    }
  }
}
</style>
