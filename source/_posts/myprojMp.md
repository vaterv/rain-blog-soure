---
title: 逆向日程表开发
date: 2022-12-17 14:53:31
updated: 2022-12-17 14:53:31
---

> 微信搜索`逆向日程`或`逆向日程表`即可找到小程序
> [项目源码](https://gitee.com/yaspayne/reverse-schedule)

## 1.开发背景

[逆向日程表的社会科学背景](https://www.bilibili.com/video/BV1cP4y1A72R)

逆向日程表以 30 分钟的番茄钟时间为目标，完成即可完成计划。以最想做的计划，有心流的事为优先的一种规划事件的方法

[逆向日程的来源](https://www2.jianshu.com/p/57978b77cb9b)

## 2.小程序引入图表数据工具 uchart

使用 DCloud 插件市场定制的 uchart 插件即可，配置方法与 echart 相同

在**ops**对象中通过修改属性值设置饼图的颜色、边框、透明度等样式

把储存在本地的日程信息获取后赋值给在**chartData**的 res.series.data;
在使用过程中发现 res.series.data 数组对象需要重新定义 var 变量赋值才会获取到实际的变量的值

## 3.设置事件优先级的颜色

本次开发使用的是 uni ui 组件并没有符合设计要求的点击切换事件栏颜色的 ui 组件，所以使用三目运算嵌套控制颜色改变

```
:style="item.type === 1 ? 'background-color:#94bcff;' : (item.type === 2 ? 'background-color:#8cde9b;' : 'background-color:#ffffff;')"
```

## 4.在开发过程中遇到 tableData.length 不是 function 的错误提示

原因是第一次在写入数组对象的值的过程中数组被转换成类数组，所以使用数组方法会报错，解决方法是使用
Array.from()方法

`this.tableData = Array.from(this.tableData)`

## 5.使用 uni ui 组件在 chrome 模拟器能改变样式而在微信开发者平台模拟的样式并没有改变

在开发者平台点击箭头查看样式 style 找到 uniui 组件的 class 名 再在自写的代码中使用 css 选择器:nth-child(2n)选中改变事件栏的样式

```
	.uni-table-td:nth-child(2n) {
		padding: 8rpx;
	}
```
