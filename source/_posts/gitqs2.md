---
title: git常用命令
date: 2021-11-14 15:53:24
updated: 2021-11-14 15:29:35
categories: 网络知识
---

## git 常用命令

1. 从服务器克隆一个仓库
   `git clone ssh://example.com/~/www/project.git`
2. 从服务器拉取一个仓库
   `git pull "仓库地址"`
3. 查看状态
   `git status`
4. 查看不同内容
   `git diff`
5. 创建并切换分支
   `git checkout -b `
6. 跳转到主分支
   `git checkout master`
7. 添加变更过的文件
   `git add "文件名"`
8. 提交变更
   `git commit "文件名" -m "版本信息"`
9. 推送到自己的分支
   `git push origin <branch>`
10. 合并分支
    `git merge "分支名"`
