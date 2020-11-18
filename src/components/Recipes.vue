<template>
  <div class="recipes mt-3">
    <b-container>
      <h1 class="text-center font-weight-bold text-danger">{{ title }}</h1>
      <b-row class="recipes__recipe-row">
        <div class="col-lg-4 col-sm-6 col-12 recipes__recipe-col"
          v-for="recipe in recipes"
          :key="recipe.title">
          <Recipe :recipe="recipe" />
        </div>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Recipe from "./Recipe";

export default {
  components: { Recipe },
  created() {
    this.fetchRecipes();
  },
  data() {
    return {
      title: "",
      recipes: [],
    };
  },
  methods: {
    async fetchRecipes() {
      try {
        const res = await fetch("https://noroffcors.herokuapp.com/http://www.recipepuppy.com/api");
        /*
        const proxy = "https://noroffcors.herokuapp.com/"; 
        const corsUrl = proxy + url; 
        */
        const data = await res.json();
        this.recipes = data.results;
        this.title = data.title;
      } catch (err) {
        console.log(err.message);
      }
    },
  },
};
</script>

<style>
.recipes__recipe-row {
  margin-top: 5rem;
  margin-bottom: -5rem;
}
.recipes__recipe-col {
  padding-bottom: 5rem;
}
</style>