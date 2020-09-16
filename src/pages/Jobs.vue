<template>
  <div id="jobs" class="container-fluid">
    <div class="row">
      <div class="col">
        <form @submit.prevent="createJob" class="form-inline">
          <div class="form-group p-1">
            <label class="mr-1" for="jobTitle">Job Title</label>
            <input
              v-model="newJob.jobTitle"
              type="text"
              name="jobTitle"
              class="form-control"
              placeholder="Job Title..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="company">Company</label>
            <input
              v-model="newJob.company"
              type="text"
              name="company"
              class="form-control"
              placeholder="Company..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="rate">Rate</label>
            <input
              v-model="newJob.rate"
              type="number"
              name="rate"
              class="form-control"
              placeholder="Rate..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="hours">Hours</label>
            <input
              v-model="newJob.hours"
              type="number"
              name="hours"
              class="form-control"
              placeholder="Hours..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="description">Description</label>
            <input
              v-model="newJob.description"
              type="text"
              name="description"
              class="form-control"
              placeholder="Description..."
            />
          </div>
          <button type="submit" class="btn btn-outline-success">Add Job</button>
        </form>
      </div>
    </div>
    <div class="row" id="data"></div>
  </div>
</template>

<script>
export default {
  name: "Jobs",
  mounted() {
    this.$store.dispatch("getAllJobs");
  },
  props: {},
  data() {
    return {
      newJob: {},
    };
  },
  methods: {
    createJob() {
      this.$store.dispatch("createJob", this.newJob);
    },
  },
  computed: {},
};
</script>

<style>
</style>