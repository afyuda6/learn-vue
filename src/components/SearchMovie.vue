<template>
  <div class="row">
    <div class="col-md-8">
      <div class="input-group mb-3">
        <input
          v-model="searched"
          type="text"
          class="form-control"
          placeholder="Input Movie Title..."
        />
        <button
          @click="searchmovie(searched)"
          class="btn btn-primary"
          type="button"
        >
          Search
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchMovie",
  props: ["search"],
  data() {
    return {
      searched: undefined,
    };
  },
  methods: {
    searchmovie(title) {
      this.$emit("searchmovie", title);
    },
  },
};
</script>