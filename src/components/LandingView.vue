<template>
    <div class="home" :style="image">
      <div class="landing">
        <div class="landing-view">
            <h1>Asheeka Samuels Portfolio</h1>
                <p>{{ jobTitle }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
  name: 'LandingView',
  computed: {
    jobTitle() {
      return this.$store.state.jobTitle; // Assuming jobTitle is an array and we want the first item
    }
  },
  mounted() {
    this.$store.dispatch('fetchjobTitle'); // Assuming 'fetchjobTitle' is the action to fetch job title data
  }
};
  </script>