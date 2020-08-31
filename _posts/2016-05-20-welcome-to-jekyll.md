---
layout: page
title:  "如何使用GitHub创建一个属于自己的博客（一）"
subtitle: "如何使用GitHub创建一个属于自己的博客（一）"
date:   2020-08-29 21:21:21 +0530
categories: [""]
---
# 一、Git是什么

## 1.1 Git简介

- 团队协作开发（中转站：GitHub：全球最大的男性交友网站）

- 分支（本地/远程）管理

- GIT，全称是分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。每个开发者可以通过克隆 git clone，在本地机器上拷贝一个完整的Git仓库。
![picture](https://img-blog.csdnimg.cn/20200830233909569.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

## 1.2 Git作用

- 代码管理

## 1.3 安装Git

- 点击此链接[https://git-scm.com/](https://git-scm.com/)进入git官网下载git

- 点击Downloads选择你所需要的版本进行下载
![picture](https://img-blog.csdnimg.cn/20200828210639732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

## 1.4 如何开始使用Git

- 下载安装之后，你会在任意一个文件夹中 右键 均可以看到git bash here在改文件夹下打开终端（自带命令行工具）

> 注：如果此时马上要在这个空白文件夹内开始一个项目，需要在'git bash here'命令行内先'git init'初始化本项目文件夹后（即本地仓库）再开始项目。
如下图所示：
![picture](https://img-blog.csdnimg.cn/2020083023480620.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
## 1.5 Git常用命令介绍

### 1.5.1 初始化本地仓库

> 有个命令叫 'git init' （初始化本地仓库—本质）：在你的项目根目录中新建了一个隐藏文件夹（'.git'）

**注：如果项目中有.git这个文件夹就不需要我们手动去初始化**

### 1.5.2 本地的代码如何提交到远程网站中

- **git add .** （将本地代码推到本地代码中的暂存区）

> 注：删除文件后需要 'git add -A', 光 'git add.' 不行，区别如下：
'git add -A' 保存所有的修改 'git add .' 保存新的添加和修改，但是不包括删除 'git add -u' 保存修改和删除，但是不包括新建文件。 所以默认使用'git add -A' 就行。

- **git commit -m “提交信息”** （将暂存区的代码正式提交到本地版本库）

> 注：此命令会将 'git add .' 存入暂存区的修改文件提交至本地仓库中，若文件未添加至暂存区，则提交时不会提交任何修改。

- **git push <远程地址> <本地分支名><:><远程分支名>** （将本地版本库中的代码提交到远程版本库）

> 注： 上面命令表示，将本地的 'master' 分支推送到 'origin' 主机的 'master' 分支。如果 'master' 不存在，则会被新建。

### 1.5.3 远程的代码如何下载/合并到本地中

当你本地还没有项目代码的时候，需要完整的下载一个远程项目，要用到此命令：

- **git clone -b 远程分支名 远程地址**

> 注：如果不加 '-b' 也就是不指定哪个分支会默认 'master' 分支）

合并某个拉取下来的分支中的代码：

- **git merge 指定远程分支**

拉取远程版本库中所有有变化的分支中的内容：

- **git fetch**

### 1.5.4 本地如何进行分支管理

查看本地有哪些分支：

- **git branch**

切换分支：

- **git checkout 分支名**

新建分支：

- **git branch 分支名**

# 二、注册GitHaub

<br>此文章原链接[https://blog.csdn.net/weixin_46323637/article/details/108287483](https://blog.csdn.net/weixin_46323637/article/details/108287483)