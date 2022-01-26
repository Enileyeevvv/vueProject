<script>

import Header from '../components/Header.vue';
import axios from "axios";

export default {
  name: 'News',
  components: {
    Header,
  },

  data() {
    return {
      articles: null,
    }
  },

  created(){
    axios
      .get ('https://vue-blog-back.herokuapp.com/articles')
      .then (
        response => (
          this.articles = response.data
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
      <div class="articles__list">
        <div class="article__item" v-for="article in articles" :key="article">
          <article class="article">
            <img :src="'/news/' + article.preview_image" :alt="article.name">
            <h2>{{article.name}}</h2>
            <p>{{article.shortDesc}}</p>
            <router-link :to="'/news/' + article.id">Посмотреть</router-link>
          </article>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
}
.article {
  max-width: 600px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  border-radius: 10px;
  border: 2px solid black;
  background-color: white;
  margin: 50px;
  padding: 10px;
}
img {
  width: 250px;
  height: 200px;
}
</style>