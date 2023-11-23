<template>
  <div
    id="app"
    class="md:flex"
  >
    <NavBar />
    <main class="md:flex flex-col">
      <Banner />
      <PageContent class="grow" />
    </main>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import Banner from "./components/Banner.vue";
import PageContent from "./components/PageContent.vue";

export default {
  name: "App",
  components: {
    NavBar,
    Banner,
    PageContent,
  },
};
</script>

<style lang="scss">
html,
body {
  height: 100%;
}

#app {
  font-family: "Noto Sans";
  height: 100%;

  main {
    height: 100%;
  }
}
</style>
