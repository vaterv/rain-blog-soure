---
title: vue知识
date: 2021-12-15 14:08:48
updated: 2021-12-15 14:08:48
categories: 网络知识
---

## vue 知识 2

1. 你是如何理解 Vue 的双向数据绑定的
   VUE 是 MVVM 模式就是 Model–View–ViewModel 模式，对于双向绑定的理解，就是用户更新了 View，Model 的数据也自动被更新了，这种情况就是双向绑定。就是在单向绑定的基础上给可输入元素 input、textare 等添加了 change(input)事件,(change 事件触发，View 的状态就被更新了)来动态修改 model。
   利用 Object.defineProperty 这个 API 实现了 Data 每个属性的监听和回调。

   数据驱动页面方向：就是当去修改 Data 某一个属时，会通知观察者，然后观察者触发自身的回调数，进而重新渲染页面。

2. MVVM 和 MVC 有什么区别

   MVC 是应用最广泛的软件架构之一
   Model(模型),View(视图),Controller(控制器)。 这主要是基于分层的目的,让彼此的职责分开。C 即 Controller 指的是页面 逻辑。
   MVC 是单向通信。也就是 View 跟 Model，必须通过 Controller 来承上启下。
   MVC 中 Controller 演变成 MVVM 中的 ViewModel
   -MVVM 通过数据来显示视图层而不是节点操作
   -MVVM 主要解决了 MVC 中大量的 dom 操作使页面渲染性能降低，加载速度变慢，影响用户体验等问题。
