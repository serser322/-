<template>
  <div
    id="app"
    class="sm:flex"
  >
    <NavBar />
    <main class="flex flex-col">
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

<style>
#app {
  font-family: "Noto Sans";
  height: 100%;

  main {
    height: 100%;
  }
}
</style>
