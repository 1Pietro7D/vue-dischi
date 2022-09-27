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
.logoContainer {
  $size: 30px;
  height: $size;
  width: $size;
  img {
    width: 100%;
  }
}
</style>
