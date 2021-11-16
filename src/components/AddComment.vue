<script>
import axios from "axios";

export default {
  name: "CommentForm",
  props: {
    name: String,
  },

  data() {
    return {
      article: null,
    };
  },

  created() {
    axios
      .get(
        "http://demo-api.vsdev.space/api/articles/" +
          this.$route.params.id +
          "/comments"
      )
      .then((response) => (this.article = response.data));
  },
};
</script>

<template>
  <div class="comment-list">
    <div class="comment-list__item">{{ article }}</div>
  </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
