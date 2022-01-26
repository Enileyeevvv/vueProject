<script>
import Header from "../components/Header.vue";
import Comments from "../components/Comments.vue";
import axios from "axios";

export default {
  name: "Article",
  components: {
    Header,
    Comments,
  },

  data() {
    return {
      article: null,
    };
  },

  created() {
    axios
      .get("https://vue-blog-back.herokuapp.com/articles/" + this.$route.params.id)
      .then((response) => (this.article = response.data));
  },
};
</script>

<template>
  <div class="news">
    <Header name="News" />
    <br /><br /><br /><br /><br />
    <div class="wrapper">

      <article v-if="article.name" class="article">
        <img
          class="article__img"
          :src="'/news/' + article.full_image"
          :alt="article.name"
        />
        <h2 class="article__title">{{ article.name }}</h2>
        <p class="article__date">{{ article.date }}</p>
        <p class="article__descr">{{ article.desc }}</p>
      </article>
      <Comments />
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
  background-color: white;
  display: flex;
  flex-direction: column;
  margin: 50px;
  padding: 10px;
}
.article__img {
  align-self: center;
  width: 50%;
  height: auto;
}
img {
  width: 500px;
  height: 400px;
}
</style>