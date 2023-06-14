<template>
  <div id="app">
    <MyNav></MyNav>
    <transition name="router-anim" mode="out-in"> <router-view/> </transition>
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

.router-anim-enter-active {
  animation: coming 0.5s;
  animation-delay: 0.5s;
  opacity: 0;
}

.router-anim-leave-active {
  animation: going 0.5s;
}

@keyframes coming {
  from {
    transform: translateX(-50px);
    opacity: 0;
  }

  to {
    transform: translateX(0px);
    opacity: 1;
  }
}

@keyframes going {
  0% {
    transform: translateX(0px);
  }

  100% {
    transform: translateX(-50px);
    opacity: 0;
  }
}
</style>
