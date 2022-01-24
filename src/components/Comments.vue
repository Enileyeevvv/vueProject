<script>
import axios from "axios";
import CommentList from "../components/CommentList.vue";
import AddComment from "../components/AddComment.vue";

export default {
  name: "Article",
  components: {
    CommentList,
    AddComment,
  },

  data() {
    return {
      article: null,
      comments: null,
    };
  },

  methods: {
    commentCreated(data){
      console.log(data)
      this.comments.push({user_name: data.user_name, comment: data.comment})

    }
  },

  created() {
    axios
      .get("http://demo-api.vsdev.space/api/articles/" + this.$route.params.id)
      .then((response) => (this.article = response.data));
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
    <div class="comments">
      <CommentList v-bind:comments="this.comments" />
      <AddComment v-on:commentCreated="commentCreated"/>
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