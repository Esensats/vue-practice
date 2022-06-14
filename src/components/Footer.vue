<template>
  <footer>
    <div class="container">
      <span>Esensats&copy;2022</span>
    </div>
  </footer>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Footer",
};
</script>

<style scoped lang="scss">
@use "@/styles";
footer {
  background-color: styles.$colorSecondaryDark;
  color: styles.$colorSecondaryNeutral;
}
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
