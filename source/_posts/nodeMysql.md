---
title: nodeMysql数据库
date: 2023-07-22 22:55:19
tags:
---
1.下载mysql npm模块
`npm i mysql --save`
2.导入mysql模块
3.连接数据库

```
文件结构
src
    -index.js
    -router.js
    -mysql.js
```

- 1.index.js
```
const express = require("express");
const app = express();
const router = require("./router");

app.use("/", router);
app.listen(4000, () => {
  console.log("服务器开启了");
});
```
- 2.router.js
```
const express = require("express");
const router = express.Router();
// 导入mysql模块
const mysql = require("mysql");
const content = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "123456",
  database: "", //数据库名称
  port: "3306", //端口号
});
router.get("/", (req, res) => {
  res.send("pl");
});
// 接口 查看所有用户信息
router.get("/", (req, res) => {
  let sql = "select * from userinfo";
  content.query(sql, (error, result) => {
    if (error) {
      console.log("数据库操作失败");
      return;
    }
    // 成功查询到数据 把结果返回给前端
    res.send(result);
  });
});
module.exports = router;
```

- 3.mysql.js
```
const mysql = require("mysql"); //1.导入
// 2.连接
const content = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: "123456",
  database: "", //数据库名称
  port: "3306", //端口号
});
// 3.编写sql语句
const sql = "select * from userinfo";

// 4.执行sql语句 参数1：数据库查错误，数据库查成功
content.query(sql, function (error, success) {
  if (error) {
    console.log("数据库操作失败");
    return;
  } else {
    console.log("ok");
  }
});
// 如果想验真，直接node运行此页面就行

```


