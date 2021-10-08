<template>
<div class="wrapper">
  <v-app>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</div>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    
  }),
}
</script>

<style scoped>
.wrapper {
  max-width: 1280px;
  margin: 0 auto
}
</style>