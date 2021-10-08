<template>
  <div class="news">
    <Header name = "News page"/>
    <list/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import List from '../components/List.vue'

export default {
  name: 'News',
  components: {
    Header,
    List,
  }
}
</script>
