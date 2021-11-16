<script>
import axios from "axios";
import CommentList from "../components/CommentList.vue";

export default {
  name: "Article",
  components: {
    CommentList,
  },

  data() {
    return {
      article: null,
    };
  },

  created() {
    axios
      .get("http://demo-api.vsdev.space/api/articles/" + this.$route.params.id)
      .then((response) => (this.article = response.data));
  },
};
</script>

<template>
  <div class="comment">
    <CommentList />
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
}
img {
  width: 500px;
  height: 400px;
}
</style>