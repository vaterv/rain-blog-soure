---
title: 在vue项目中用axios请求数据的方法
date: 2021-10-10
updated: 2021-10-10
categories: 手册
---

## 在 vue 项目中用 axios 请求数据的方法

1. 创建 vue 项目
   `vue create myaxios`
2. 安装 axios 包
   `npm i axios`
3. 在 vue 项目的 main.js 中导入
   `import Axios from 'axios'`
4. 挂载到 vue 上
   `Vue.prototype.$axios = Axios`
5. 此时就可以用 this.$axios 来使用了
6. 直接发起请求,here im using get way

```
   this.$axios({
   method: "GET",
   url: "http://localhost:3000/search/hot/detail",
   })
   .then((resp) => {
   console.log("111 后端有返回");
   console.log(resp);
   })
```

7. 如果控制台打印出数据，我们第一次在 vue 的 axios 请求就成功了 嘻嘻
