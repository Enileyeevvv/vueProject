<script>
export default {
  name: 'Header',
  props: {
    name: String
  }
}
</script>

<template>
    <div class="header">
        <div class="header-inner">
          <div class="menu">
            <div class="logo">
              <router-link to="/"><img src = "../pic/logo.jpg"></router-link>
            </div>
            <div class="nav">
              <router-link to="/">Home</router-link> |
              <router-link to="/about">About</router-link> |
              <router-link to="/news">News</router-link>
            </div>
          <router-view/>
          <div class="search">
            <input class="search-input" type="text" value="   Поиск:">
            <button class="search-btn">
              <img class="search-img" src="../pic/magnifier.svg">
            </button>
          </div>
          </div>
          <div class = "header-name">
            <h1>{{ name }}</h1>
          </div>
        </div>
      </div>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*, *:after, *:before {
  margin: 0;
  padding: 0;  
}

.wrapper {
  max-width: 1280px;
  margin: 0 auto;
}

.menu {
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color:rgb(80, 80, 80);
}

img {
  max-width: 100px;
  max-height: 100px;
  border-radius: 100%;
}

.search{
  display: flex;
  justify-content: center;
  align-items: center;
}

.search-input{
  height: 25px;
  border: 3px solid black;
  border-radius: 15px;
}

.search-btn{
  width: 25px;
  height: 25px;
  border: 2px solid black;
  border-radius: 15px;
  margin: 0px 0px 0px 10px;
}

.search-img{
  width: 15px;
  height: 15px;
}

.header-name {
  display: flex;
  justify-content: center;
}

</style>
