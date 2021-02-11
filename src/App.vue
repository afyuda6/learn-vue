<template>
  <div id="app">
    <div class="container">
      <Header />
      <SearchMovie v-on:searchmovie="searchmovie" />
      <Movie v-bind:search="search" v-on:detailmovie="detailmovie" />
      <MovieDetail v-bind:detail="detail" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Header from "./components/Header";
import SearchMovie from "./components/SearchMovie";
import Movie from "./components/Movie";
import MovieDetail from "./components/MovieDetail";

export default {
  name: "App",
  components: {
    Header,
    SearchMovie,
    Movie,
    MovieDetail,
  },
  data() {
    return {
      search: undefined,
      detail: {
        Poster: undefined,
        Title: undefined,
        Year: undefined,
        Director: undefined,
        Actors: undefined,
        Writer: undefined,
        Plot: undefined,
      },
    };
  },
  methods: {
    detailmovie(id) {
      axios
        .get("https://www.omdbapi.com/?apikey=8f658eda&i=" + id + "/")
        .then((res) => {
          this.detail = res.data;
          console.log(this.detail);
        })
        .catch((err) => console.log(err));
    },
    searchmovie(name) {
      axios
        .get("https://www.omdbapi.com/?apikey=8f658eda&s=" + name + "/")
        .then((res) => {
          this.search = res.data.Search;
          this.search = this.search.filter(
            (searched) => searched.Poster != "N/A"
          );
          console.log(this.detail);
        })
        .catch((err) => console.log(err));
    },
  },
};
</script>