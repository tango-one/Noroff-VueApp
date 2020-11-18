<template>
  <div class="recipes__recipe h-100">
    <div no-body class="card border-0 h-100" style="max-width: 540px">
      <div class="d-flex flex-column justify-content-between h-100">
        <div class="text-center recipes__recipe__img-container mb-4">
          <b-card-img-lazy
            :src="recipe.thumbnail"
            :alt="recipe.title"
            class="rounded-circle"
          ></b-card-img-lazy>
        </div>
        <b-card-body
          :title="recipe.title"
          class="p-3 d-flex flex-column justify-content-end"
        >
          <b-card-text>
            <div>
              {{ recipe.ingredients }}
            </div>
            <a
              :href="recipe.href"
              class="btn btn-outline-danger d-block w-100 mt-3"
              >Full recipe</a
            >
          </b-card-text>
        </b-card-body>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    recipe: {
      type: Object,
      required: true,
    },
  },
};
</script>


<style>
.recipes__recipe .card {
  box-shadow: 0 0 4px 2px rgba(0, 0, 0, 0.08), 0 0 12px 4px rgba(0, 0, 0, 0.08);
}
.recipes__recipe__img-container {
  margin-top: -3.75rem;
}
.recipes__recipe__img-container img {
  max-width: 7.5rem;
}
.recipes__recipe .card-body {
  background-color: rgba(0, 0, 0, 0.01);
}
</style>