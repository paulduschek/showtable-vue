<template>
  <div id="app">
    <img alt="Vue logo" src="https://vuejs.org/images/logo.png">
    <PostList/>
  </div>
</template>

<script>
import PostList from './components/PostList.vue';

export default {
  name: 'App',
  components: {
    PostList, 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

img{
  width: 7em;
  display: block;
  margin-left: auto;
  margin-right: auto;
}

h2{
  text-align: center;
}
</style>
