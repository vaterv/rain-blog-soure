---
title: vue知识1
date: 2022-02-01 18:32:30
updated: 2022-02-01 18:32:30
categories: 网络知识
---

## vue 知识

1.  可以把一些简单的 js 指令放在 v-on 里面
    `<button v-on :click="counter +=1 ">Add 1</button> `
    `<el-button type="primary" @click="innervisibleImg = true">上传图片</el-button>`

2.  vue 的生命周期
    生命周期就是从摇篮到坟墓的整个过程，在 Vue 中实例从创建到销毁的过程，即指从创建、初始化数据、编译模板、挂载 Dom→ 渲染、更新 → 渲染、卸载等一系列过程我们可以把组件比喻成工厂里面的一条流水线。
    Vue 生命周期总共可以分为 8 个阶段:创建前后, 载入前后,更新前后,销毁前销毁后，以及一些特殊场景的生命周期.
    生命周期有哪些

| 生命周期                | 描述                                        |
| ----------------------- | ------------------------------------------- |
| beforeCreate,created    | 组件实例被创建之初,组件实例已经完全创建     |
| beforeMount,mounted     | 组件挂载之前,组件挂载到实例上去之后         |
| beforeUpdate,updated    | 组件数据发生变化，更新之前,组件数据更新之后 |
| beforeDestroy,destroyed | 组件实例销毁之前,组件实例销毁之后           |
| activated               | keep-alive 缓存的组件激活时                 |
| deactivated             | keep-alive 缓存的组件停用时调用             |
| errorCaptured           | 捕获一个来自子孙组件的错误时被调用          |

3.  VUE 中如何避免样式冲突？
    使用 scope 和 组件模块化

4.  v-if 和 v-show 的区别？

    - v-if 是根据它其后跟的条件是否为真来决定是否渲染，内容只会在指令的表达式返回 trut 值的时候被渲染.v-if 是惰性的，如果初始条件为假，则什么也不做；只有在条件第一次变为真时才开始局部编译;
    - v-show 是已经渲染出来，用样式控制是否可见的,用于根据条件展示元素的选项是 v-show 指令(频繁切换时使用)
      v-show 是在任何条件下，无论首次条件是否为真，都被编译，然后被缓存，只是简单地切换元素的 CSS property display

5.  Vue2 怎么监听响应数据变化
    在 vue2.x 版本中，数据监听是用过 Object.defineProperty 这个 API 来实现的
    我们访问或设置对象的属性的时候，都会触发相对应的函数，然后在这个函数里返回或设置属性的值。
    我们当然可以在触发函数的时候做我们自己想做的事情，这也就是“劫持”操作
    在 Vue 中其实就是通过 Object.defineProperty 来劫持对象属性的 setter 和 getter 操作，并创建一个监听器，当数据发生变化的时候发出通知。

6.  怎么理解 Vue 的 key?

    key 就是一个标识，被使用在 Vue 中。再详细一点，key 被使用在 Vue 中的虚拟 DOM 中 1.只做数据展示用，不写 key 是没有任何影响的;
    2.key 不会出现在真实 DOM 中
    key 是给每一个 vnode(虚拟节点)的唯一 id，也是 vue 的 diff 算法（是一种逻辑）的一种优化策略。可以根据 key，更准确，更快的找到对应的 vnod 节点

7.  VUE 的 nexttrick
    如果没有 nextTick 更新机制，那么 num 每次更新值都会触发视图更新(上面这段代码也就是会更新 10 万次视图)，有了 nextTick 机制，只需要更新一次，所以 nextTick 本质是一种优化策略

8.  $router和$route 的区别

    - Rotuer 是一个实列，用来实现路由跳转、操作路由
      this.$router.push 等
    - route 获取当前路由的信息的，查看数据的详情

9.  什么是 Virtual DOM
    Virtual DOM 是一种可以预先通过 JavaScript 进行各种计算，把最终的 DOM 操作计算出来并优化，由于这个 DOM 操作属于预处理操作，并没有真实的操作 DOM，所以叫做虚拟 DOM

10. 为什么要选择 vue.js 它解决了什么问题

    Vue 有声明式，响应式的数据绑定，与组件化的开发，并且还使用了 Virtual DOM,使用了 mvvm 模式，实现了双向绑定，使数据和视图的更新更为流畅，让前端应用程序开发方便。
    它用来构建用户界面,Vue 的核心库只关注视图层，不仅易于上手，还便于与第三方库或既有项目整合。
    引入 Virtual DOM 会加大 Vue.js 本身的代码尺寸，也会消耗更多内存和 CPU（会更耗电）

    > <https://www.jianshu.com/p/6307e4ed4cf4>

11. Vue.js 中组件是如何通信的

| 通信方法     | 详细                                                                            |
| ------------ | ------------------------------------------------------------------------------- |
| props 父传子 | 父组件在子的标签中通过字面量传递值，子组件设置['props']属性来接收               |
| $emit 子传父 | 子组件用$emit 触发，第二个参数就是要传的值父组件 绑定监听器获取子组件传来的参数 |
| Vuex         | 用于复杂关系的组件数据传递,vuex 相当于一个储存共享变量的容器                    |

- State :存放共享变量
- Getter:store 中的计算属性，获取共享变量的值
- Mutations:存放修改 state 的方法
- Actions:异步修改 state
