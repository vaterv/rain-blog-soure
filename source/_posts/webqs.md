---
title: web知识
date: 2021-12-15 14:53:31
updated: 2021-12-15 14:53:31
categories: 网络知识
---

## web 相关知识 web 相关知识

1. Package.json 有什么用
   定义了这个项目所需要的各种模块，以及项目的配置信息（比如名称、版本、许可证等元数据）。npm install 命令根据这个配置文件，自动下载所需的模块，也就是配置项目所需的运行和开发环境

2. 对 webpack 的使用有哪些优化建议
   • 缩小打包作用域
   • 充分利用缓存，提升二次构建速度
   • 使用高版本的 webpack

   > 来自 <https://blog.csdn.net/qq_44722915/article/details/109101979>

3. 重绘和回流有什么区别
   - 重绘
     当 render tree 中的一些元素需要更新属性，而这些属性只是影响元素的外观，风格，而不会影响布局的，比如 background-color。则就叫称为重绘。
   - 回流
     当 render tree 中的一部分(或全部)因为元素的规模尺寸，布局，隐藏等改变而需要重新构建。这就称为回流(reflow)。每个页面至少需要一次回流，就是在页面第一次加载的时候，这时候是一定会发生回流的。
   - 区别
     回流必将引起重绘，而重绘不一定会引起回流。比如：只有颜色改变的时候就只会发生重绘而不会引起回流
   - 比如：添加或者删除可见的 DOM 元素，元素位置改变，元素尺寸改变——边距、填充、边框、宽度和高度，内容改变
4. web 前端的优化策略

   1. 减少不必要的消耗时间的 Http 请求数，是 web 前端开发技术的一个重要方面
   2. 优化文件的规模，这个过程包括压缩 JavaScript 和 CSS 文件以及对相应的代码进行优化。
   3. 减少 DNS 查找 DNS 查找的时间开销很大，这是国内许多网站的通病。
   4. 优化网页内容根据 CSS 这样的特性，要实现 web 的优化，可以考虑将样式表放在顶部。另外，可以将 script 放在底部，该举措是为了防止 script 脚本阻塞当前页面，从而造成下载速度较慢，页面的加载时间过长等问题的产生

5. 响应式布局是什么，如何实现响应式布局
   响应式布局:是同一页面在不同的屏幕上有不同的布局，即只需要一套代码使页面适应不同的屏幕

   1. 原生代码

   - 百分比布局
   - 媒体查询使用@media

   ```
       @media screen and (min-width: 768px){ /*大于等于768*/
       body{
           background-color: red;
       }
   }
   ```

   2. 框架

   - elementui 的 24 栅格
   - Bootstrap 提供了一套响应式、移动设备优先的流式栅格系统，随着屏幕或视口（viewport）尺寸的增加，系统会自动分为最多 12 列
