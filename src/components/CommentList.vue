<script>
import axios from "axios";

export default {
  name: "CommentList",
  props: {
    name: String,
  },

  data() {
    return {
      comments: null,
    };
  },

  created() {
    axios
      .get(
        "http://demo-api.vsdev.space/api/articles/" +
          this.$route.params.id +
          "/comments"
      )
      .then((response) => (this.comments = response.data));
  },
};
</script>

<template>
  <div class="wrapper">
    <div class="comment-list">
      <h2 class="comment-list__header">Комментарии</h2>
      <div
        class="comment-list__item"
        v-for="comment in comments"
        :key="comment"
      >
        <h3 class="comment-list__user-name">{{ comment.user_name }}</h3>
        <p class="comment-list__user-comment">{{ comment.comment }}</p>
      </div>
    </div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapper {
  max-width: 1280px;
  margin: 0 auto;
}
.comment-list {
  background-color: #f5f5f5;
  padding: 50px;
}
.comment-list__header {
  padding-bottom: 50px;
}
.comment-list__user-name {
  background-color: #ffffff;
  border: 1px solid grey;
  padding: 15px;
}
.comment-list__user-comment {
  background-color: #fafafa;
  border: 1px solid grey;
  border-top: none;
  padding: 15px;
}
</style>
