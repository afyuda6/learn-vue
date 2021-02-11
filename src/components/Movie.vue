<template>
  <div class="row movie-container">
    <div
      class="col-md-2 my-3"
      v-bind:key="movie.imdbID"
      v-for="movie in search"
    >
      <div class="card">
        <img v-bind:src="movie.Poster" class="card-img-top" />
        <div class="card-body">
          <h5 class="card-title">{{ movie.Title }}</h5>
          <h6 class="card-subtitle mb-2 text-muted">{{ movie.Year }}</h6>
          <button
            @click="detailmovie(movie.imdbID)"
            class="btn btn-primary"
            data-bs-toggle="modal"
            data-bs-target="#movieDetailModal"
          >
            Show Details
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Movie",
  props: ["search"],
  methods: {
    detailmovie(id) {
      this.$emit("detailmovie", id);
    },
  },
};
</script>