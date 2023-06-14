<template>
  <div id="app">
    <MyNav></MyNav>
    <router-view/>
  </div>
</template>

<script>
import MyNav from './components/MyNav.vue'

export default {
  components:{
    MyNav,
  },
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  background-color: #2c3e50;
  background-image: url("https://supportivy.com/wp-content/uploads/2020/08/pixel-art-wallpaper-Idees-designs-photo-6.jpg");
  background-repeat:repeat;
  height: 100%;
  min-height: 100vh;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #ffffff;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
