<template>
  <div class="home">
    <baseInput />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import baseInput from '../components/baseInput.vue'
export default {
  name: 'Home',
  components: {
    baseInput,
  },
}
</script>
