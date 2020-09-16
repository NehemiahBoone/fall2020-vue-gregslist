<template>
  <div id="job-details" class="container">
    <div class="row pt-3" v-if="job._id">
      <div class="col-6">
        <h2>{{job.jobTitle}} - {{job.company}}</h2>
        <h3>{{job.rate}}</h3>
        <p>{{job.description}}</p>
        <div class="d-flex justify-content-between">
          <button class="btn btn-outline-danger" @click="deleteJob">Delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    return this.$store.dispatch("getJobById", this.$route.params.id);
  },
  name: "Job-Details",
  mounted() {
    this.$store.dispatch("getJobById", this.$route.params.id);
  },
  data() {
    return {};
  },
  methods: {
    deleteJob() {
      this.$store.dispatch("deleteJob", this.job._id);
    },
  },
  computed: {
    job() {
      return this.$store.state.activeJob;
    },
  },
};
</script>

<style>
</style>