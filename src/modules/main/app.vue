<template>
  <div id="app">
    <Header :title="pageTitle" noBackBtn="true"></Header>
    <h1>这里是{{title}}页面</h1>
    <a :href="href.url">==>{{href.name}}</a>
    <img :src="img">
    <hello></hello>
  </div>
</template>

<script>
import mui from 'mui'
// 引入mui的css,目前会导致build的时候编译无法通过
import '@/assets/css/mui.css'
import Header from '@components/Header'
import Hello from '@components/Hello'

export default {
  name: 'app',
  data () {
    return {
      pageTitle: '科技文献检索',
      href: {
        url: './index.html',
        name: 'index'
      },
      // 本地图片如果放在assets中,url-loader会无法识别他.会导致图片无法显示
      img: './static/logo.png'
    }
  },
  mounted () {
    console.log(this.title)
    console.log(mui)
  },
  components: {
    Header,
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
</style>
