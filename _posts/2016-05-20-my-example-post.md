---
layout: page
title:  "如何使用GitHub创建一个属于自己的博客"
subtitle: "如何使用GitHub创建一个属于自己的博客（一）"
date:   2020-08-28 21:21:21 +0530
categories: ["general"]
---

# 一、Git是什么
Git，全称是分布式版本控制系统,可以有效、高速的处理从很小到非常大的项目版本管理。每个开发者可以通过克隆**git clone**,在本地机器上拷贝一个完整的**Git**仓库。
# 二、安装Git
- 点击此链接[Git官网](https://git-scm.com/)进入到Git官网下载并且安装Git
- 点击Downloads选择你所需要的版本进行下载
![Git下载图片](https://img-blog.csdnimg.cn/20200828210639732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
- 下载安装之后，你会在任意一个文件夹中点击右键均可看到"**git bash here**"这个命令行工具
![图片](https://img-blog.csdnimg.cn/20200828210932769.png#pic_center)
## 如何开始使用Git这个终端呢
- 打开**git bash here** 这个终端后有个命令叫**git init**（初始化本地仓库-本质）：会在你的项目根目录中新建一个隐藏文件夹(.git)
**注：如果项目中有.git这个文件夹就不需要我们手动去初始化**