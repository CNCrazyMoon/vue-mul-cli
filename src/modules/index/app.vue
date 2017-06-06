<template>
  <div id="app">
    <h1>这里是index页面</h1>
    <a href="./login.html">==>login</a>
    <img src="../../assets/logo.png">
    <hello></hello>
  </div>
</template>

<script>
import Hello from '@components/Hello'

export default {
  name: 'app',
  components: {
    Hello
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.hello {
  display: flex;
}
</style>
