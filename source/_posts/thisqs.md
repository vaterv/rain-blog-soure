---
title: JS中的this关键词
date: 2022-05-15 15:09:24
updated: 2022-05-15 15:09:24
categories: 网络知识
---

## 如何理解 JS 中的 this 关键词

- this 表示当前对象的一个引用,代表函数运行时，自动生成的一个内部对象,JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变

1. 全局作用域下-this 默认指向 window,在浏览器中测试可知，全局作用下 this 指向是指向 window
2. 直接调用普通函数-this 指向 window 对于直接调用普通函数，this 的指向一定是 window
3. 通过对象调用函数-谁调用函数，this 指向谁
4. 显式绑定-bind、call、apply 显式绑定后，this 会明确的指向绑定对象
5. 调用 new 关键词创建的对象实例的函数
   构造函数或 Class 类，可以通过 new 关键词创建的对象实例，这时 this 永远的指向了实例化的对象上面
6. ES6 中箭头函数（()=>{}）没有 this、arguments、super 等，不受上边的规则限制，这些只依赖包含箭头函数最接近的函数中的规则，也就是外层作用域来决定 this。
