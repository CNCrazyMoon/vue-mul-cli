<template>
  <div id="app">
    <h1>index阿萨德客户</h1>
    <a href="./login.html">==>index</a>
    <a href="./main.html">==>main</a>
    <img src="../../assets/logo.png">
    <hello></hello>
    <div class="k">
      asdhjl
    </div>
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

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.k {
  display: flex;
}
</style>
