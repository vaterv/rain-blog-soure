---
title: 什么是tcp
date: 2021-11-10 09:49:30
updated: 2021-11-10
categories: 网络知识
---

## 什么是 tcp

Tcp/ip 网络最常用的**通信协议**,是当今互联网的常用标准.它完成一次通信的 5 个步骤叫做 5 个层
![图片](https://tse3-mm.cn.bing.net/th/id/OIP-C.piOczJGdSOBWEtAbvRdLZwAAAA?w=234&h=180&c=7&r=0&o=5&dpr=1.5&pid=1.7)

由图可以知道它是从数据下潜到物理，此协议的特征之一就是将数据分割成**小包发送**,分割后的各个数据叫做数据包.也因此这样的通信被叫做数据包通信。

- 传输数据的流程
  ![图片](https://tse4-mm.cn.bing.net/th/id/OIP-C.3BMpoRJ35AMKjH2K3qQ4LQFgCx?w=335&h=168&c=7&r=0&o=5&dpr=1.5&pid=1.7)

发送数据是封包 打包的过程是不断加头的过程
接收方是做与发送方相反的过程即拆包
