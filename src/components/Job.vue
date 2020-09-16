<template>
  <div class="col-4 job">
    <div class="card">
      <div class="card-body">
        <h4 class="card-title">{{}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Job",
  props: {},
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