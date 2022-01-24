<script>

export default {
  name: "CommentList",
  props: {
    name: String,
    comments: Array,
  },

  data() {
    return {
    };
  },
};
</script>

<template>
  <div class="comment-list">
    <h2 class="comment-list__header">Комментарии:</h2>
    <div class="comment-list__item" v-for="comment in comments" :key="comment">
      <h3 class="comment-list__user-name">{{ comment.user_name }}</h3>
      <p class="comment-list__user-comment">{{ comment.comment }}</p>
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
