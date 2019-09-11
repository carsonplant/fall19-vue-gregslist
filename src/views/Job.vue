<template>
  <div class="job">
    Job Details
    <h1>{{job.company}}</h1>
    <h5>{{job.title}}</h5>
    <h5>{{job.hours}}</h5>
    <h5>{{job.rate}}</h5>
    <h5>{{job.description}}</h5>
    <button class="btn btn-danger" @click="delete">Delete Job</button>
  </div>
</template>


<script>
  export default {
    name: 'job',
    data() {
      return {}
    },
    mounted() {
      let payload = {
        jobId: this.$route.params.jobId
      };
      this.$store.dispatch("getJobById", payload);
    },
    computed: {
      car() {
        return this.$store.state.activeJob;
      }
    },
    methods: {
      delete() {
        this.$store.dispatch("deleteJob", this.job._id);
      }
    },
    components: {}
  }
</script>


<style scoped>

</style>