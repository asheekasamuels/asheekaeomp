<template>
  <div class="container about-container">
    <h1>About</h1>
    <div class="row">
      <div class="col">
        <img src="https://asheekasamuels.github.io/All-Images/images/Asheeka3.jpg" alt="keira" class="img-fluid w-75" loading="lazy">
      </div>
      <div class="col d-flex flex-column justify-content-center align-items-center">
        <p v-for="(item, index) in about" :key="index">{{ item }}</p>
        <Spinner v-if="!about.length"/>
      </div>
    </div>
  </div>
</template>

<script setup>
import Spinner from './Spinner.vue'
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
const store = useStore()
const about = computed(() => store.state.about)
onMounted(() => {
  store.dispatch('fetchAbout')
})
</script>
