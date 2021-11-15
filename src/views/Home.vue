<script>

import Header from '../components/Header.vue';
import Slider from '../components/Slider.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Slider,
  },
}

</script>

<template>
  <div class="home">
    <Header name = "Home"/>
    <br><br><br><br><br>
    <Slider/>
  </div>
</template>

<style scoped>

</style>