<template>
  <div class="col-4 job">
    <router-link :to="{name: 'JobDetails', params: {id: jobData._id}}">
      <div class="card">
        <div class="card-body">
          <h4 class="card-title">{{jobData.jobTitle}} - {{jobData.company}}</h4>
          <p>{{jobData.description}}</p>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Job",
  props: {
    jobData: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {},
  computed: {},
};
</script>

<style scoped>
.job {
  transition: 0.5s ease;
  cursor: pointer;
}
.job:hover {
  transform: scale(1.05);
}
</style>