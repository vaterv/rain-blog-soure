---
title: VUE知识2
date: 2021-08-08
updated: 2021-08-08
---

## 1.什么是 MVVM 模式

MVVM 是 Model、view、view-model 的缩写。

- Model 代表数据层，用于存储数据和对数据进行增删改查
- view 代表视图层，即 UI 界面，用于将数据模型转化成 UI 展现出来
- view-model 通过双向数据连接前两者。当 Model 数据改变时通过它改 View 变视图层;反之 View 视图层改变时通过它改变 Model 数据层

## 2.双向数据绑定的原理

Vue 数据双向绑定原理是通过**数据劫持**结合**发布者-订阅者**模式的方式来实现的。首先对数据进行**监听**，然后当监听的属性发生变化时则告诉**订阅者**是否要更新，若更新就会执行对应的**更新函数**从而更新视图

## 3.数据劫持的原理

通过“Object.defineProperty()”方法来劫持各个属性的 setter，getter，在数据变动时发布消息给订阅者，触发相应的监听回调,来更新函数

## 4.vue 和 react 的区别？

1. **组件写法差异**

   - React 推荐的做法是 JSX + inline style, 也就是把 HTML 和 CSS 全都写进 JavaScript 中,即 all in js
   - Vue 推荐的做法是 template 的单文件组件格式(简单易懂，从传统前端转过来易于理解),即 html,css,JS 写在同一个文件(vue 也支持 JSX 写法)

2. **diff 算法不同**

   - Vue2 的核心 Diff 算法采用了双端比较的算法，同时从新旧 children 的两端开始进行比较，借助 key 值找到可复用的节点，再进行相关操作。
   - React 的 Diff 算法，是传统 Diff 算法循环递归每一个节点。同样情况下可以 Vue 的 diff 算法减少移动节点次数，减少不必要的性能损耗

3. **响应式原理不同**
   - Vue 自动优化，数据可变。当数据改变时，自动找到引用组件重新渲染
   - React 基于状态机，手动优化，数据不可变，需要 setState 驱动新的 state 替换老的 state
