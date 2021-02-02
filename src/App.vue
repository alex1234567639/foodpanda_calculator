<template>
  <div id="app">
    <HelloWorld msg="今晚，我想來點..."/>
    <img class="img" alt="Vue logo" src="./assets/uberEat.png">
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.img {
  width: 900px;
}
</style>
