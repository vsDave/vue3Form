<template>
  <div id="nav">
    <!-- <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
    <simpleForm></simpleForm>
  </div>
  <!-- <router-view /> -->
</template>

<script>
import simpleForm from '../src/views/simpleForm.vue'
export default {
  components: {
    simpleForm,
  },
}
</script>
