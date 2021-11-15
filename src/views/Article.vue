<script>

import Header from '../components/Header.vue';
import axios from "axios";

export default {
  name: 'Article',
  components: {
    Header,
  },

  data() {
    return {
      article: null,
    }
  },

  created(){
    axios
      .get ('http://demo-api.vsdev.space/api/articles/' + this.$route.params.id)
      .then (
        response => (
          this.article = response.data
        )
      )
    },
  }
</script>

<template>
  <div class="news">
    <Header name = "News"/>
    <br><br><br><br><br>
    <div class="wrapper">
        <article class="article">
          <h2>{{article.name}}</h2>
        </article>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  max-width: 1280px;
  margin: 0 auto;
}
.article {
  border-radius: 10px;
  border: 2px solid black;
  background-color: #F3F1F5;
  margin: 50px;
  padding: 10px
}
</style>