<template>
  <div class="news">
    <Header name = "News page"/>
    <div class="news-list">
      <div class="wrapper">
        <div class="news-list-inner">
          <NewTemplate v-for="item in news" :key="item.id" :item="item" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import NewTemplate from '../components/NewTemplate.vue'

export default {
  name: 'News',
  components: {
    Header,
    NewTemplate,
  },
  data() {
    return {
      news: null,
    };
  },
};
</script>