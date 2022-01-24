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
      username: null,
      comment: null,
    };
  },
  
  methods: {
    addComment(e) {
      e.preventDefault()
      axios.defaults.headers.post['Access-Control-Allow-Origin'] = '*';
      axios
        .post(
        `http://demo-api.vsdev.space/api/articles/${this.$route.params.id}/comments`,
          {
            user_name: this.username,
            comment: this.comment,
          },
      )
      this.$emit(`commentCreated`, {user_name: this.username, comment: this.comment})
    }
  },
};
</script>

<template>
  <form class="add-comment" method="post" @submit="addComment">
    <h2 class="form__header">Оставить комментарий:</h2>
    <input class="form__name" type="text" name="name" v-model="username" required="required" />
    <textarea class="form__comment" name="comment" v-model="comment"></textarea>
    <button class="form__add-btn" type="submit">Оставить Комментарий</button>
  </form>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.add-comment {
  display: flex;
  flex-direction: column;
  padding: 50px;
}
.form__header {
  margin-bottom: 30px;
}
.form__name {
  width: 30%;
  height: 50px;
  background-color: #ffffff;
  border: 1px solid grey;
  margin-bottom: 30px;
  padding: 15px;
}
.form__comment {
  resize: none;
  width: 60%;
  height: 100px;
  background-color: #ffffff;
  border: 1px solid grey;
  margin-bottom: 30px;
  padding: 10px;
}
.form__add-btn {
  width: 225px;
  color: white;
  background-color: red;
  padding: 10px;
}
</style>
