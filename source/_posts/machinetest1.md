---
title: JS问题2
date: 2022-05-23
updated: 2022-05-23
---

## 某表单公司机试题

## 1.数据排序

假设有如下字符串“A12”，其中“A”表示数据类型(A-Z) ，“12”表示数据序号(0-9) 。现在需要对一组数据先按照数据序号再按照数据类型进行排序。
例如: ["B3","D2","F1","A9","D12","A2","C1","Z0'","B1"]=>["Z0","B1","C1","F1","A2","D2","B3","A9","D12"]

我的答案

```
var unorderData = ["B3", "D2", "F1", "A9", "D12", "A2", "C1", "Z0", "B1"];
// 排序结果
var orderedData = unorderData.sort().sort(function (a, b) {
  return a.slice(1) - b.slice(1);
});

```

## 2. 局部页面实现（必答题）

页面设计图：点此查看[设计图](https://www.figma.com/file/TpilpjXkaDUOw6sm1EogqP/%E5%89%8D%E7%AB%AF%E9%A1%B5%E9%9D%A2%E5%B8%83%E5%B1%80?node-id=0%3A1&t=ueel6JWr5T0P2UZK-0)
请实现以上设计图中的页面内容。要求：

1. 一比一还原设计图
2. 不可以使用 table
3. 最小支持页面宽度为：1024px

- 使用了 flex 嵌套布局实现表单样式，justify-content 实现一行 item 在水平方向的对齐；align-item 实现一列 item 在竖直方向上的对齐。
- class 类 CSS 样式复用
