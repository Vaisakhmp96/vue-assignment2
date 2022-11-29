<template>
  <div id="app">
   <postData></postData>
  </div>
</template>

<script>
import postData from './components/postData.vue'

export default {
  name: 'App',
  components: {
    postData
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
</style>
