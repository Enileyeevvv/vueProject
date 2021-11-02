<script>

import Header from '../components/Header.vue';

export default {
  name: 'News',
  components: {
    Header,
  },
};

</script>

<template>
  <div class="gallery">
    <Header name = "Gallery"/>
    <br>
    <br>
    <br>
    <div class="wrapper">
      <div class="gallery-inner">
        <img src="../pic/tokyo1.jpg">
        <img src="../pic/tokyo2.jpg">
        <img src="../pic/tokyo3.jpg">
        <img src="../pic/tokyo3.jpg">
        <img src="../pic/tokyo1.jpg">
        <img src="../pic/tokyo2.jpg">
        <img src="../pic/tokyo2.jpg">
        <img src="../pic/tokyo3.jpg">
        <img src="../pic/tokyo1.jpg">
        <img src="../pic/tokyo1.jpg">
        <img src="../pic/tokyo2.jpg">
        <img src="../pic/tokyo3.jpg">
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  max-width: 1280px;
  margin: 0 auto;
}
.gallery-inner {
  flex-wrap: wrap;
  max-width: 1280px;
  display: flex;
  justify-content: space-around;
}
.gallery-inner img{
  min-width: 50px;
  max-width: 400px;
  height: auto;
  border-radius: 10px;
  margin-bottom: 30px;
}

</style>