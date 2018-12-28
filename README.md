<h3 align="center">如何创建一个使用parcel打包的vue项目</h3>

1. 创建一个`项目文件夹`(比如 `parcel-iview-demo`)来放置我们需要的文件

2. 在刚才创建好的`项目文件夹`里面执行 `yarn init` 来创建一个 `package.json`

3. 在`项目文件夹`里面执行 `yarn add parcel` 安装项目需要的依赖 (是的，只要这一个)

4. 在`项目文件夹`里面创建一个`源码文件夹`(比如 `src`)来放置我们代码

5. 在`源码文件夹`里面创建三个文件 `index.html` `index.js` `app.vue`

文件内容如下

index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>parcel-iview-demo</title>
</head>
<body>
  <div id="app"></div>
</body>
<script src="/index.js"></script>
</html>
```

index.js
```js
import Vue from 'vue';
import iView from 'iview';
import 'iview/dist/styles/iview.css';

import App from './app.vue';

Vue.use(iView);

new Vue({
  el: '#app',
  render: h => h(App)
});

```

app.vue
```html
<template>
  <div style="background:#eee;padding: 20px">
    <Card :bordered="false">
      <p slot="title">Happy with parcel</p>
      <p>Just a demo.</p>
    </Card>
  </div>
</template>
<script>
export default {};
</script>
```

6. 在`项目文件夹`下执行 `yarn parcel src/index.html`，parcel 会启动一个 dev server
   会出现类似 `Server running at http://localhost:1234` 的提示，浏览器访问这个网址即可


- parcel 有 autoinstall 所以你可以不安装其他依赖，parcel会自动帮你安装未安装的依赖
- parcel 允许你在 html 里面引用未编译的文件 (JavaScript, TypeScript, SCSS) 它会帮你编译好并替换这些引用
- 其他事宜参见 [官方文档](https://parceljs.org/)

