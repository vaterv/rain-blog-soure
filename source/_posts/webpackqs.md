---
title: webpack使用
date: 2022-01-14 17:29:25
updated: 2022-01-14 17:29:25
categories: 网络知识
---

## webpack 使用

    webpack是用来打包的,打包好放在dist文件夹里。

### 背景

上面讲到的前端这些新的技术，其实是无法直接运行源码的，必须通过转换后才能正常运行。另一方面，现在前端工程师需要维护的代码变得及为庞大和复杂，代码维护、打包、发布等流程也变得极为繁琐，同时浪费的时间和精力也越来越多，当然人为的错误也随着流程的增加而增加了更多的出错率。致使每一个团队都希望有一种工具，能帮助整个团队在开发中能精简流程、提高效率、减少错误率。

grunt、gulp、webpack、Parcel、vite 都是常见的打包工具

### 优点

·代码转换:TypeScript 编译成 JavaScript、SCSS 编译成 CSS 等。
·文件优化:压缩 JavaScript、CSS、HTML 代码，压缩合并图片等。
·代码分割:提取多个页面的公共代码、提取首屏不需要执行部分的代码让其异步加载。
·模块合并:在采用模块化的项目里会有很多个模块和文件，需要构建功能把模块分类合并成一个文件。·自动刷新:监听本地源代码的变化，自动重新构建、刷新浏览器。
·代码校验:在代码被提交到仓库前需要校验代码是否符合规范，以及单元测试是否通过。
·自动发布:更新完代码后，自动构建出线上发布代码并传输给发布系统。

### webpack 配置

1. 在项目文件夹中安装 webpack
   `npm i -D webpack webpack-cli`

> npm i -D 为 npm install --save-dev 的缩写
> npm i -s 为 npm install --save 的缩写

2. 新建一个文件夹 src ,然后新建一个文件 main.js,写一点代码测试一下
   `console.log( 'Hello world')`

3. 配置 package.json 命令

```
"scripts": {
"build" :"webpack ./src/main.js"}
```

4. 执行 npm run build
   此时如果生成了一个 dist 文件夹，并且内部含有 main.js 说明已经打包成功了.
