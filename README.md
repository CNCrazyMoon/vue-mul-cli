# vue-mul-cli

> 基于vue-cli的多页配置实例

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

### 概述

- 简单修改了`entries` 和 `HtmlWebpackPlugin`,实现了多页配置.
- 配置`alias`,实现快速访问
- 增加`scss`语法支持
- 增加`postcss` `autoprefix`支持,打包的样式文件会自动补全css
- 增加页面`titile`的配置,参考`page.conf.js`

其他内容后续补充

### 一些tips
在引入第三方库的时候,比如`UI组件库`等,个人觉得应该放在static中,避免重复编译,拖慢编译速度.




For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
