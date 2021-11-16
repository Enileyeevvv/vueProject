<script>
import axios from "axios";

export default {
  name: "Slider",
  data() {
    return {
      articles: null,
      status: null,
      colors: ["indigo", "indigo", "indigo", "indigo", "indigo", "indigo"],
    };
  },

  created() {
    axios.get("http://demo-api.vsdev.space/api/articles").then(
      (response) =>
        (this.articles = response.data
          .filter((el) => el.slider === true)
          .map((el) => {
            let len = el.name.split("").length;
            if (len > 30) {
              return el.name.split("").splice(0, 26).join("") + " ...";
            } else {
              return el.name;
            }
          }))
    );
  },
};
</script>

<template>
  <div>
    <v-carousel
      height="500"
      cycle
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="(article, i) in articles" :key="i">
        <v-sheet :color="colors[i]" height="100%">
          <v-row class="fill-height" align="center" justify="center">
            <div class="text-h2">
              {{ article }}
            </div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<style scoped>
</style>>