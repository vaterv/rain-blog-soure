---
title: 封装前端请求头
date: 2022-01-01 21:14:42
updated: 2022-01-01
categories: 网络知识
---

## 封装前端请求头

- 1.引入 axios 安装包对象 npm 包
- 2.新建 Utils/axios.js
- 3.在里面自定义配置新建一个实例

```
const instance = axios.create({ baseURL: 'https://some-domain.com/api/', timeout: 1000, headers: {'X-Custom-Header': 'foobar'} });
```

- 4.配置请求拦截器对象.属性和对象[‘属性’]这两个用法的意义其实是一样的，都是用来调用对象的属性。config 里面就包括请求头，在这里统一配一个请求头

```
axios.interceptors.request.use(config =>{console.log(config)
let token = sessionstorage.getItem( 'mytoken');
//从浏览器中，获取token的值
token &&(config.headers[ 'token'] = token);
//自己添加一个token到Headersreturn config;
//少写一行代码,则不能实现axios接口调用。
}, error => Promise.reject(error));

```

- 5.设置响应拦截器

```
axios.interceptors.response.use(response=>i
console.log(response)
//先观察响应对象的SON结构，怎么样可以拿到token?下一行就相应的进行修改
response.data.token && sessionStorage.setItem('mytoken', response.data.token);
return response.data;
//决定了在调用接口时，如何获取到数据，如何判断是否调用成功。},
error=>{
let res = error.response;
switch(res.status){
// http请求的状态码，其中401，代表token认证失败。case 401:
sessionstorage.removeItem( ' mytoken ');
// return router.push("/login" )
//跳转到登录页面
};
```

- 6.在 main.js 中引入刚刚封装的 axios

```
import Axios from './util/axios.js '
Vue.prototype.$axios = Axios;
```
