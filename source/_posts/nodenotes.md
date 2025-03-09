---
title: node搭建最简单的服务器
date: 2021-12-11
updated: 2021-12-11
---

## node 搭建最简单的服务器

1. 引入 http 模块
   `var http = require("http")`
2. 创建监听，在有请求时，发送一个响应

```
    http.createServer(function(request, response) {
    response.writeHead(200, { 'Content-Type': 'text/plain' });    // 发送响应数据 "Hello World"
    response.end('Hello World\n');
    }).listen(8888);

```

- 在服务器后台看打印一下
  `console.log('server runing in my server');`
