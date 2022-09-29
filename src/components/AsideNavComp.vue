<template>
  <aside>
    <nav>
      <div class="icon" id="search">
        <img src="@/assets/img/search.svg" alt="" />
      </div>
    </nav>
  </aside>
</template>

<script>
export default {
  name: "AsideNavComp",
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
aside {
  background-color: $asideNav_theme;
  width: $asideNav_size_w;
  padding: 3rem;
  .icon {
    $size: 50px;
    height: $size;
    width: $size;
    img {
      width: $size;
      height: $size;
      object-fit: scale-down;
      filter: invert(1);
    }
  }
}
</style>
