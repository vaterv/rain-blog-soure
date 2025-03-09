---
title: cookie是什么
date: 2022-01-01 23:32:21
updated: 2022-01-01 23:32:21
---

## cookie

Cookie 类型为小型文本文件，是某些网站为了辨别用户身份，进行 Session 跟踪而储存在用户本地终端上的数据（通常经过加密），cookie 出现就是来弥补 HTTP 无状态的问题的，Cookie 可以作为一个状态保存的状态机，用来保存用户的相关登录状态

> cookie 和 token 的区别 https://juejin.cn/post/7111349594625146887

## cookie 储存形式

Cookie 以名/值对形式存储 username=John Doe，当浏览器从服务器上请求 web 页面时， 属于该页面的 cookie 会被添加到该请求中。服务端通过这种方式来获取用户的信息。

## 在 VUE 中使用 cookie

- 1 安装
  `npm install vue-cookies --save`
- 2 引入
- 3 设置全局配置，设置 cookie 过期时间和 url
- https://www.jianshu.com/p/60c13168cc8f

## session 是什么

客户端请求服务端，服务端（Tomcat）会为这次请求开辟一块内存空间，这个对象便是 Session 对象， 存储结构为 ConcurrentHashMap。

session 的目的：弥补 HTTP 无状态特性，服务器可以利用 session 存储客户端在同一个会话期间的一些操作记录。

##　 vue 使用 session

> https://www.cnblogs.com/instead-everyone/p/14611589.html
