---
title: node 1小时速成课
date: 2023-07-21 01:30:41
tags:
---
```
// console.log(module);
// 1.使用我导出的
// 导入
// const logger=require('./logger')
// console.log(logger);
// logger.log('woaini')
// console.log(__filename);
// console.log(__dirname);
// 2.使用path模块 获得路径
// const path=require('path');
// var pathObj=path.parse(__filename)
// console.log('pathObj: ', pathObj);
// 3.获取操作系统
// const os =require('os')
// const totalmen=os.totalmem()
// console.log('totalmen: ', totalmen);
// 4.fs 文件系统
// const fs=require('fs')
// const files=fs.readdirSync('./') //同步 阻塞的
// console.log('files: ', files);
// 异步
// fs.readdir('￥',function (err,files) {
//     if (err) console.log('Error',err)
//     else console.log('result',files);
// })
// 5.events 事件模块
// const EventEmitter=require('events') //大驼峰书写 表示这是一个class :is a contaiber of a bunch of methods
// const emitter=new EventEmitter(); //class is huamna,object is mary
// // 创建一个listner
// emitter.on('messageLogged',function (params) {
//     console.log('lister called',params);
// })
// emitter.emit('messageLogged','雨晴辛苦了')
// 6.定义一个class
// class Logger extends EventEmitter{
// log(message){
//     console.log('message: ', message);
// // emitter.emit('messageLogged','雨晴辛苦了')
// this.emit('messageLogged','雨晴辛苦了')
// }}

// module.exports=Logger //导出class
// 7.HTTP模块
// const http=require('http')
// const server=http.createServer()
// server.on('connection',()=>{
//     console.log('NEW CONNECTION.....');
// })
// const server=http.createServer((req,res)=>{
//     //req是请求对象，包含了与客户端相关的数据和属性 
//     //req.url是客户端请求路径 req.method是客户端请求的method类型
//     if(req.url==='/'){
//         res.write('heyyy');
//         res.end() //向客户端响应一些内容,并结束这次请求
//     }
// })
// const server=http.createServer((req,res)=>{
//     console.log('url',req.url,'method',req.method);
// res.end('url')
// })
// server.listen(3000) //启动服务器的方法
// console.log('listening on port http://127.0.0.1');

// 8.commentJs 规范
// a。module变量代表当前模块
// b.moudule变量是一个对象，moudule.exports 是对外接口
// c.加载模块用require方法
```