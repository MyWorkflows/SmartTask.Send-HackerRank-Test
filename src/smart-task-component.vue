<script lang="ts">
import { defineComponent } from "vue";


export default /*#__PURE__*/ defineComponent({
  name: "SmartTaskComponent", // vue component name
  props: ['componentState', 'componentStatus'],
  data() {
    return { model: {} };
  },
  computed: {},
  methods: {
    async submitForm() {
      this.$emit("execute-smart-task", this.model);
    },
  },
  created() {
    if (this.componentState) {
      this.model = this.componentState;
    }
  },
  setup() {},
});
</script>


<template>
  <form>
    <div class="d-flex flex-row bd-highlight mb-3">
      <div class="mx-4">
        <div class="mb-3">
          <img
            width="100px"
            src="https://res.cloudinary.com/dbwpvgyrn/image/upload/c_scale,w_300/v1643297464/myworkflows/HackerRank_logo.png"
          />
        </div>
      </div>
      <div class="w-100">
        <div class="mb-3">
          <label class="form-label">Candidate Email Address</label>
          <input
            type="email"
            placeholder="email@myworkflows.io"
            class="form-control"
          />
          <div class="form-text">
            Specify the email address for the user completing the assignment.
          </div>
        </div>
        <div class="mb-3">
          <label class="form-label">Due By Date</label>
          <input type="datetime-local" class="form-control" />
          <div class="form-text">
            Specify the date when the assignment is due by.
          </div>
        </div>

        <div class="mb-4">
          <h4 class="form-label">Assignments</h4>
          <div class="my-2 py-1 row">
            <div class="col-md-6">
            <div class="me-1 card">
              <div class="card-body">
                <h5>
                  Top Competitors <span class="badge bg-warning">Medium</span>
                </h5>
                <ul>
                  <li>SQL (Intermediate)</li>
                  <li>Max Score: <span class="fw-bold">30</span></li>
                  <li>
                    Success Rate: <span class="badge bg-success">96.16%</span>
                  </li>
                </ul>
              </div>
            </div>
              </div>
          <div class="col-md-6">
            <div class="card">
              <div class="card-body">
                <h5>
                  Cards Permutation
                  <span class="badge bg-danger">Expert</span>
                </h5>
                <ul>
                  <li>Algorithms</li>
                  <li>Max Score: <span class="fw-bold">85</span></li>
                  <li>
                    Success Rate: <span class="badge bg-success">60.35%</span>
                  </li>
                </ul>
              </div>
            </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <button type="submit" class="float-end btn btn-success">
      Email Assignment
    </button>
  </form>
</template>

