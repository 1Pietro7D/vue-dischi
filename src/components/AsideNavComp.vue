<template>
  <aside>
    <nav></nav>
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
  width: 300px;
  background-color: $asideNav_theme;
}
</style>
