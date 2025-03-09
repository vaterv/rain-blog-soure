---
title: express安装过程中出错
date: 2021-09-10 13:20:54
updated: 2021-09-10
---

## express 安装过程出错

| 问题                                                                     | 找到的原因                                                           |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------- |
| If you believe this might be a permissions issue,please double-check the | 这个要用管理员权限打开 vscode                                        |
| npm start npm ERR! Missing script: "start"                               | 这个是我们刚刚创建了一个 express 文件 但是我们没有进入该文件 cd demo |
| Error: Cannot find module 'cookie-parser'Require stack:                  | 重新创建一个就没有问题了                                             |
