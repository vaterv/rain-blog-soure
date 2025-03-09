---
title: node + express in 3 hours笔记
date: 2023-07-21 21:30:41
tags:
---

1. npm init //项目初始化，创建package.json 配置文件
2. npm i express --save //--save 模块会被保存到pacakge.json的dependence中 缩写 npm i -S
    -- save -dev//下载的包会被保存到package.json的dev,只是开发环境需要 缩写：npm i -D
    -g 全局安装
3.package-lock.json 是包的详细信息
4.安装cnpm
    1.npm i -g cnpm --registry=https://registry.npm.taobao.org
    2.检测 cnpm -v 不报错就ok
5.路由
    -使用express的方法，导出，use
    -文件结构:
    ```
    src
        -index.js
        -router.js
        -package.json
    public
        -css
            -reset.css
    ```
    ```
    // 1.导入express的router功能
const express = require("express");

// 2.创建路由器
const router = express.Router();

// 3.创建路由地址--配路由
// router.get("/", (req, res) => {
//   res.send("首页接口数据");
// });
// 轮播接口
router.get("/banner", (req, res) => {
  res.send("轮播接口数据");
});

// 获取路由参数 get方法
router.get("/", (req, res) => {
  //req.query是前端传来的参数
  // 后端可以定义接受变量名称
  let user = req.query.username; //username是我定义的变量名
  let pwd = req.passwaord;
  console.log(req);
  res.send({
    user,
    pwd,
  });
});
// 获取路由参数 post方法 req.body获得，此外还要app.use(express.urlencoded({extendsd:true}))这个中间件 编码
router.post("/login", (req, res) => {
  let user = req.body.user;
  if (user == "admin") {
    user.code = 200;
    res.send(user);
  } else {
    user.code = 400;
    res.send(user);
  }
});
// 导出路由模块
module.exports = router;

    ```
    index.js:
    ```
    const express = require("express");
const app = express();

// 1.静态文件托管
app.use("/", express.static("../public")); //把图片等文减价暴露出来 在get访问时就不必写public,直接/就能访问里面的东西 localhost:/8000/css
// 2.路由模块化

// 导入路由文件
const router = require("./router");

// /一级接口 /banner二级接口
// app.use("/api", router); //访问localhost/api/路径地址才能访问的router文佳里的东西

// post 请求处理的中间件
app.use(express.urlencoded({ extended: true })); //

// 使用这个路由 app.use('/根路径',资源)
app.use("/", router);

// 开启服务器
app.listen(80, () => {
  console.log("服务器开启了");
});

    ```
6.express 处理get请求
    引入index.js时，app.use('/这个路由文件的跟路径',暴露出来的对象)
7.get请求传参
    router方法的req.query是前端传来的参数
    post方法 req.body获得，此外还要app.use(express.urlencoded({extendsd:true}))这个中间件 编码
8.静态文件托管
    app.use("/", express.static("../public")); //访问图片等
9.连接数据库
  

