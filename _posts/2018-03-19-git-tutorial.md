---
layout: post
title: git常用命令
date: 2018-03-19
categories:
- tool
tags: [转换器, 云跟帖，disqus]
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  views: '2'
author:
  login: slayer
  email: dongyado@gmail.com
  display_name: slayer
---

#### git 是一种分布式版本管理工具，特点是git分支管理，与开源的远程仓库github配合使用。

#### Trick: 区分工作目录、暂存区域、本地仓库、远程仓库
---

- [ ] 基本命令
```cpp
git init
git add readme.txt
git commit -m "wrote a readme file"
git remote add origin https://github.com/Hacker-vision/itchat-master.git //using https
或git remote add origin git@github.com:Hacker-vision/leetcode.git //using ssh,可能会遇到publickey的问题
git push -u origin master 
```
- [ ] 可能用到的命令
```cpp
git clone https://github.com/Hacker-vision/itchat-master.git
git config --global user.name "ajksunkang"
git config --global user.email "ajksunkang@pku.edu.cn"
git pull origin master //远程仓库有更新
```
- [ ] 查看状态|日志
```cpp
git status
git log
```
- [ ] 回退版本
```cpp
git reset --hard HEAD^
git reset --hard 3628164
git reflog                 //回退后返回最新版本
```
- [ ] 分支管理
```cpp
git branch new_branch       //创建 new branch
git checkout new_branch     //切换 branch
git branch                  //查看 branch情况
git merge new_branch        //合并 branch
git branch -d new_bacnch    //删除 old branch
```

trygit 15分钟教程：[https://try.github.io](https://try.github.io)


