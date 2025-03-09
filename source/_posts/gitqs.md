---
title: git笔记
date: 2021-11-14 15:29:35
updated: 2021-11-14 15:29:35
categories: 网络知识
---

## git 笔记

1. 什么是 git
   git 是管理代码版本的工具，是分布式版本控制系统即订可以保存我们每一次的修改记录。而 github 是放代码口中央服务器，类似的还有 gitee

2. Git 与 SVN 区别
   1、Git 是分布式的，SVN 不是：这是 Git 和其它非分布式(分布式即版本库在自己电脑上)的版本控制系统，例如 SVN，CVS 等，最核心的区别。
   2、Git 把内容按元数据方式存储，而 SVN 是按文件：所有的资源控制系统都是把文件的元信息隐藏在一个类似 .svn、.cvs 等的文件夹里。

3. 如何创建 git 本地仓库并与远程仓库连接
   1. 初始化本地仓库 `git init `
   2. 设置邮箱和姓名要和远程仓库中的一致
      `git config --global user.email "邮箱"`
      `git config --global user.name "姓名"`
   3. 配置 SSH`ssh-keygen -t rsa -C "邮箱名称"`
   4. 成功之后，打开 C:\Users\Administrator\.ssh 目录下的 id_rsa.pub 文件复制文件内容
   5. Gitee/GitHub 官网登录 setting->SSH
