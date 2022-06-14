<template>
  <Header title="Практика" />

  <router-view class="main"/>

  <Footer />
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
};
</script>

<style lang="scss" scoped>
.main {
  flex: 1 1 auto;
}
</style>

<style lang="scss">
@use "@/styles";
</style>
