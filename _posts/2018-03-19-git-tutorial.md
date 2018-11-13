---
layout: post
title: Linux & git常用命令
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
git remote set-url origin https://github.com/Hacker-vision/itchat-master.git //using https
或git remote add origin git@github.com:Hacker-vision/leetcode.git //using ssh,需要本地生成秘钥，在SSH服务器上注册,优点是不用每次都输入密码
git push -u origin master 
```
- [ ] 可能用到的命令

```cpp
git clone --branch new_branch https://github.com/Hacker-vision/itchat-master.git new-diretory[指定目录，缺省会创建与远程仓库名相同的目录名]
git config --global user.name "ajksunkang"
git config --global user.email "ajksunkang@pku.edu.cn"
git pull origin master //远程仓库有更新
git clean -d -fx //暂存区域的文件修改全部删除
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

---
### Linux命令备忘录

- [ ] apt-get安装和卸载命令

```cpp
apt-get update                          //更新源
apt-get upgrade                         //升级软件
apt-get install software_name           //安装软件
apt --reinstall install software_name   //强制重新安装
apt-get --purge remove  software_name   //卸载软件及其配置
apt-get autoremove software_name        //卸载软件及其依赖的安装包
```
- [ ] diff & patch

1.单个文件
```cpp
diff –uN  from-file  to-file  > to-file.patch  //创建补丁
patch –p0 < to-file.patch                      //打补丁
patch –RE –p0 < to-file.patch                  //清除补丁
```
2.多个文件
```cpp
diff –uNr  old_docu  new_docu >  myfirst.patch  //创建补丁
cd old_docu/
patch –p1 < ../myfirst.patch                    //打补丁
patch –R –p1 < myfirst.patch                     //清除补丁
```

- [ ] 查看服务器配置

```cpp
lscpu                          //处理器信息
free -m                        //内存大小（MB）
df -h                          //硬盘大小
```
- [ ] U盘挂载
```cpp
lsblk                          //打印块设备
mkdir /mnt/fat32/
sudo mount /dev/sdb1 /mnt/fat32
sudo umount /mnt/fat32
```

- [] 查看文件大小
```cpp
du -h --max-depth=0 vmlinux    //查看某个文件or目录的字节大小
```

- [] 软连接
```cpp
ln -s 源目录或文件 新链接文件

```
