---
title: css布局
date: 2021-10-27 22:30:46
updaed: 2021-10-27 22:30:46
categories: 网络知识
---

## 1.左侧固定右侧自适应？

- flex-grow 都设置为 1
  - flex-grow：这是 项目 的一个属性，定义了项目的放大 比例，如果为 0，即使有剩余空间也不会放大。 Flex-grow:1 设置它的放大比例为 1
- `width: calc(100% - 300px);`
  算一下
- float+margin-left，左侧宽度 ml 固定

## 2.aspect-ratio CSS 新增长宽比

`aspect-ratio: width / height`
//aspect-ratio: 1 / 2;

## 未知宽高元素，如何实现居中？

- 父元素 flex 盒子设置
  `justify-content:center; align-items:center;`
- 父组件 `display: flex;`子组件设置`Margin: auto;`

##　怎么垂直居中

- 1 Flex
  `Display:flex;align(使成为直线)-items:center`
- 2 Table-cell
  父元素

```display: table-cell;
text-align: center;
vertical-align: middle;
```

- 3 Absolute 与 margin:auto
  父元素
  `position: relative;`
  子元素

```
position: absolute;
left: 0;
top: 0;
bottom:0;
right:0;
margin:auto;
```

- 4 Grid

## 屏幕三等分

- 1 flex 布局
  容器
  `display: flex;`
  组件
  `width: 33.3%;`

- 2 float
  子组件

```
width: 33.3%;
float: left;
```

- 3 父元素 display:table + 子元素 display:table-cell

## 屏幕四等分

- 1 flex 布局
  容器
  `display: flex;`
  组件
  `width: 25%;`

- 2 float
  子组件

```
width: 25%;
float: left;
```

- 3 父元素 display:table + 子元素 display:table-cell

## 如何垂直水平居中一个元素

- 1 父相子绝,子元素设置
  margin:auto
  left/right/top/bottom:0

- 2 父`Display:Table-cell;vertical-align:middle`
  子：`margin:0 auto;`

- 3 父`display:flex;justify(两端对齐)-content:center;align-items:center`
