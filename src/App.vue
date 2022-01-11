<template>
  <div id="app">
    <Header />
    <main>
      <FilmList />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import FilmList from "./components/FilmList.vue";

export default {
  name: "App",
  components: {
    Header,
    FilmList,
  },
};
</script>

<style lang="scss">

</style>
