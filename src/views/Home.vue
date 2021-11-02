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
    <Header name = "Home page"/>
    <br>
    <br>
    <br>
    <br>
    <br>
    <div class="slider-inner">
      <Slider/>
    </div>
  </div>
</template>

<style scoped>

</style>