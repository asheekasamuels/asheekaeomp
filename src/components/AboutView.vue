<template>
  <div class="container p-3" id="about">
  <h1 id="heading">About Me</h1>
  <div class="infoBlocks container-fluid">
    <div class="leftSide">
      <div class="text-col" v-if="about">
        <p class="lead" v-for="about in about" :key="about">{{ about }}</p>
      </div>
    </div>
    <div class="rightSide">
      <div class="pic-col">
        <img src="https://asheekasamuels.github.io/All-Images/images/Asheeka3.jpg" alt="Asheeka3" class="pic img-fluid">
      </div>
    </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'AboutView',
  computed: {
    about(){
      return this.$store.state.about
    }
  },
  mounted(){
    this.$store.dispatch('fetchAbout')
  }
};
</script>