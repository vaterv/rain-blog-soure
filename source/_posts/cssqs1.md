---
title: css新增特性
date: 2021-11-14 00:20:17
categories: 网络知识
---

1. CSS3 新特性有哪些

   - 新增了一些选择器:nth-child(n)
     :last-child
   - 新增边框属性
     boreder-radius:创圆角边框
     border-sahdow:为素添加阴影
   - 文字 word-wrap：normal 使用浏览器默认换行
     break-all 允许在单词内换行
     文字换行

2. Css 选择器权重
   - !important >内联样式>id 选择器>class 类选择器>元素选择器
3. Css 兄弟选择器
   |选择器|详细|
   |---|---|
   |+选择器|如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器 div+p|
   |~ 选择器|作用是查找某一个指定元素的后面的所有兄弟结点。|
   |Div p|选择 div 元素内所有的 p|
   |div,p|选择所有 div 和 p 元素|

4. css 子选择器
   p:first-child
   指定只有当 p 元素是其父级的第一个子级的样式
   p:Nth-child(2)
   选择每个 p 元素是其父级元素的第二个子元素
5. 伪类和伪元素

- 伪类
  伪类 a:hover{}
  ○ hover 鼠标移上去的状态
  ○ Link 未访问链接的状态
  ○ Visited 已访问链接的标签状态
  Activie 链接被瞬间激活时的状态
  伪元素
  类似于行内元素
  伪元素::before
