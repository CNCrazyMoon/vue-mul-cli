# vue-mul-cli

> 基于vue-cli的多页配置实例

https://github.com/CNCrazyMoon/vue-mul-cli.git

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

- 修改了`entries` 和 `HtmlWebpackPlugin`,实现了多页配置.
- 配置`alias`,实现快速访问
- 增加`scss`语法支持
- 增加`postcss` `autoprefix`支持,打包的样式文件会自动补全css
- 增加页面`titile`的配置,参考`page.conf.js`
- 支持 `hot-reload`,编辑器保存后浏览器自动刷新

其他内容后续补充

### 一些tips
~~在引入第三方库的时候,比如`UI组件库`等,个人觉得应该放在static中,避免重复编译,拖慢编译速度.~~

实际上,如果将库文件放在`static`中,因为没有经过webpack处理,而是直接copy,可能会导致在dev环境中,无法使用库文件中的内容,比如,`jQuery`的代码无效


在vue-cli中引入图片不能正常显示?
url-loader无法解析js动态生成的路径。
如果引用了本地图片,且是变量的话,应当把图片放在static下.
如果不是变量,直接书写 `<img src="../../assets/logo.png">`是没有问题的


#### 引入第三方js库的方式
<strong>使用类似vendor的方式</strong>

```js
// webpack.base.conf.js 配置 entry
entry: {
   vendor: ['vue'],
   mui: path.resolve(__dirname, libs+'/mui/mui.js')
}
```

```js
new HtmlWebpackPlugin({
    chunks: ['vendor','mui',entry],
    filename: entry + '.html',
    template: 'src/template/index.html',
    ```
})
```

2. 使用 `CommonsChunkPlugin` 实现
可以配置实现: 当文件被公共引用 N 次,则抽离打包成公用文件

3. 方式三
在 template.html 中直接写静态地址,也可以用于加载CDN中的文件
```html
<script src="./static/libs/mui.min.js"></script>
```
在`webpack.conf.base.js`中设置 `externals`,
其中后面的value值对应第三方js库的外部变量,比如window.Zepto
```js
  externals: {
    //添加外部文件的引用 
    'zepto': 'Zepto',
    'mui': 'mui'
  },
```

在需要使用的时候正常引入
```js
//比如
import mui from 'mui'
import zepto from 'zepto'
```


For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
