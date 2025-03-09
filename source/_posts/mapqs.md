---
title: vue项目中使用百度地图接口
date: 2022-09-10 00:12:33
updated: 2022-09-10
---

## vue 项目中使用百度地图接口

1. 注册百度地图的开发者帐号并拿到密钥
2. 简单应用地图
   引入
   `<script type="text/javascript" src="https://api.map.baidu.com/api?v=1.0&type=webgl&ak=您的密钥">`

创建地图实例

```
 var map = new BMapGL.Map("container");// 创建地图实例
    var point = new BMapGL.Point(116.404, 39.915);// 创建点坐标
    map.centerAndZoom(point, 15);// 初始化地图，设置中心点坐标和地图级别
```

> 参考 https://blog.csdn.net/TeAmo__/article/details/123901089
