<template>
  <div id="app">
    <Header />
    <main>
      <Content />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";

export default {
  name: "App",
  components: {
    Header,
    Content,
  },
  data() {
    return {
      options: [],
    };
  },
};
</script>

<style lang="scss">
@import "./scss/style.scss";
</style>
