<template>
  <header>
    <div class="container">
      <h2>
        <router-link to="/">{{ title }}</router-link>
      </h2>
      <nav>
        <router-link to="/">Home</router-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Header",
  props: {
    title: String,
    // example: {
    //   type: String,
    //   default: "Default value",
    // },
  },
};
</script>

<style scoped lang="scss">
@use "@/styles";
%activeLink {
  color: styles.$colorPrimaryDarker;
  border-bottom: none;
}
header {
  background-color: styles.$colorPrimaryLight;

  h2 a {
    color: inherit;
    text-decoration: none;
    &:hover {
      color: inherit;
    }
    &.router-link-exact-active {
      color: inherit;
    }
  }

  nav {
    a {
      font-weight: bold;
      text-decoration: none;
      border-bottom: 2px solid styles.$colorSecondaryDark;

      &:hover {
        @extend %activeLink;
      }
      &.router-link-exact-active {
        @extend %activeLink;
      }
    }
  }
}
.container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
