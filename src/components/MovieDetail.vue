<template>
  <div
    class="modal fade"
    id="movieDetailModal"
    data-bs-backdrop="static"
    data-bs-keyboard="false"
    tabindex="-1"
    aria-labelledby="movieDetailModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-lg modal-dialog-centered">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="movieDetailModalLabel">Show Detail</h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <div class="container-fluid">
            <div class="row">
              <div class="col-md-3">
                <img v-bind:src="detail.Poster" class="img-fluid" />
              </div>
              <div class="col-md">
                <ul class="list-group">
                  <li class="list-group-item">
                    <h4>{{ detail.Title }} ({{ detail.Year }})</h4>
                  </li>
                  <li class="list-group-item">
                    <strong>Director :</strong> {{ detail.Director }}
                  </li>
                  <li class="list-group-item">
                    <strong>Actors :</strong> {{ detail.Actors }}
                  </li>
                  <li class="list-group-item">
                    <strong>Writer :</strong> {{ detail.Writer }}
                  </li>
                  <li class="list-group-item">
                    <strong>Plot :</strong><br />{{ detail.Plot }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            data-bs-dismiss="modal"
          >
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MovieDetail",
  props: ["detail"],
};
</script>