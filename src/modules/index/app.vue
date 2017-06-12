<template>
  <div id="app">
    <h1>index页面</h1>
    <a href="./login.html">==>login</a>
    <a href="./main.html">==>main</a>
    <img src="../../assets/images/logo.png">
    <hello></hello>
    <div class="k">
     .vue文件样式测试
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
