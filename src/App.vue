<template>
  <div id="app">
    <Recipes msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import Recipes from "./components/Recipes.vue";

export default {
  name: "App",
  components: {
    Recipes,
  },
};
</script>

<style>
@media (max-width: 1199px) {
  body {
    font-size: 90%;
  }
}
@media (max-width: 991px) {
  body {
    font-size: 85%;
  }
}
@media (max-width: 767px) {
  body {
    font-size: 80%;
  }
}
@media (max-width: 575px) {
  body {
    font-size: 75%;
  }
}
</style>
