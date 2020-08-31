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

> 注：如果此时马上要在这个空白文件夹内开始一个项目，需要在 `git bash here` 命令行内先 `git init` 初始化本项目文件夹后（即本地仓库）再开始项目。
如下图所示：
![picture](https://img-blog.csdnimg.cn/2020083023480620.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

## 1.5 Git常用命令介绍

### 1.5.1 初始化本地仓库

> 有个命令叫 `git init` （初始化本地仓库—本质）：在你的项目根目录中新建了一个隐藏文件夹（`.git`）

**注：如果项目中有.git这个文件夹就不需要我们手动去初始化**

### 1.5.2 本地的代码如何提交到远程网站中

- **git add .** （将本地代码推到本地代码中的暂存区）

> 注：删除文件后需要 `git add -A`, 光 `git add.` 不行，区别如下：
`git add -A` 保存所有的修改 `git add .` 保存新的添加和修改，但是不包括删除 `git add -u` 保存修改和删除，但是不包括新建文件。 所以默认使用`git add -A` 就行。

- **git commit -m “提交信息”** （将暂存区的代码正式提交到本地版本库）

> 注：此命令会将 `git add .` 存入暂存区的修改文件提交至本地仓库中，若文件未添加至暂存区，则提交时不会提交任何修改。

- **git push <远程地址> <本地分支名><:><远程分支名>**（将本地版本库中的代码提交到远程版本库）

> 注： 上面命令表示，将本地的 `master` 分支推送到 `origin` 主机的 `master` 分支。如果 `master` 不存在，则会被新建。

### 1.5.3 远程的代码如何下载/合并到本地中

当你本地还没有项目代码的时候，需要完整的下载一个远程项目，要用到此命令：

- **git clone -b 远程分支名 远程地址**

> 注：如果不加 `-b` 也就是不指定哪个分支会默认 `master` 分支）

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

## 2.1 注册GitHub账号

1）打开[http://github.com](http://github.com)进入到github这个界面进行注册

2）点击`Sign up`切换到注册页,填写好注册信息后点击 `Sign up for GitHub` 注册

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831002606825.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

## 2.2 配置SSH
 **作用：为了免密码登陆，但也得需要一个“凭证”（电脑凭证：指代你的这台正在使用的电脑）在命令行中输入以下命令**
  

 1. 首先查看你的电脑中是否有这个凭证

> cat ~/.ssh/id_rsa.pub

 2. 生成该凭证

> ssh-keygen -t rsa -C "输入你的邮箱

```bash
注：此邮箱为你在Github注册时的邮箱（仅作为标识）
```

3. 生成之后获取凭证

> cat ~/.ssh/id_rsa.pub

 4. 把生成的凭证添加到github里面

4.1）首先在个人中心点击`settings`进入到个人界面下拉选择`SSH and GPG keys`在右上角有个叫`New SSH keys`（新的密钥）点击进去添加`SSH`密钥

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831004758735.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

# 三、GitHub Pages

## 3.1 什么是GitHub Pages

GitHub的超高人气和强大的功能，但是对于一个新手来说，看到一大堆源码，只会让人头晕脑涨，不知何处入手。他希望看到的是，一个简明易懂的网页，说明每一步应该怎么做。因此，github就设计了Pages功能，允许用户自定义项目首页，用来替代默认的源码列表。所以，github Pages可以被认为是用户编写的、托管在github上的静态网页。

GitHub Pages的一些功能：

```bash
1. 让一个小白能够快速的认知代码，感受到代码给你带来的快乐
2. 程序员的福利--用最简单的语言上线自己的一个项目
3. 它提供了我们一个域名，github的服务器中的一部分空间
```
**github提供模板，允许站内生成网页，也允许用户自己编写网页，然后上传。有意思的是，这种上传并不是单纯的上传，而是会经过Jekyll程序的再处理。**

## 3.2 博客页面的一个主题网站（Jekyll）

### 3.2.1 jekyll是什么

jekyll是一个简单的免费的Blog生成工具。是一个生成静态网页的工具，不需要数据库支持。但是可以配合第三方服务。最关键的是jekyll可以免费部署在Github上，而且可以绑定自己的域名

好处：

```bash
1. 免费，无限流量。
2. 享受git的版本管理功能，不用担心文章遗失。
3. 你只要用自己喜欢的编辑器写文章就可以了，其他事情一概不用操心，都由GitHub处理。
```
缺点：

```bash
1. 有一定技术门槛，你必须要懂一点git和网页开发；
2. 生成的是静态网页，添加动态功能必须使用外部服务，比如评论功能就只能用disqus。
3. 不适合大型网站，因为没有用到数据库，每运行一次都必须遍历全部的文本文件，网站越大，生成时间越长。
```
### 3.2.2 jellky配置

_config.yml文件：这是需要使用者进行自定义的文件，项目中会进行读取。

## 3.3 创建博客主题网站

### 3.3.1 创建博客页面

 1）点击 [http://jekyllthemes.org](http://jekyllthemes.org/)进入到jekyll页面选择一个自己喜欢的模板，在点击`HomePage`按钮进入`GitHub`项目仓库

 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831012554853.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

2）点击右上角的`fork`按钮（把这个项目复制到我们自己的仓库中来）

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831012811526.png#pic_center)

3）fork之后修改仓库名

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831013637335.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

### 3.3.2 访问博客页面

通过上面的操作，就可以在浏览器访问博客页面啦~

例如，访问我新建的博客页面：[https://yueshuai00.github.io/](https://yueshuai00.github.io/)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831014353818.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

### 3.3.3把远程仓库代码克隆到本地

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831015256649.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
在命令行窗口里paste（粘贴），再跟上一个文件夹名称，回车即开始克隆

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831023629538.png#pic_center)

### 3.3.4 HTML CSS 的使用

#### 1）HTML的结构

HTML不属于一种标准的图灵完备语言（图灵完备语言：可以参与任何情况下的计算的语言）
- HTML仅仅是一种标记，这标记不是符号，是被一组尖括号包裹着的英文单词,这样的一组标记称之为标签。基本格式如下：

```html
<标签名 属性名1=“属性值” 属性名2=“属性值”>内容</标签名>
```

- HTML的属性————根据不同的属性设置可以展示出不同的效果
除了常见的双标签外还有一些标签，采用单标签的形式，例如 ：`<meta />`

#### 2）网络请求的初步认知

请求地址：任何一个请求”都需要“完整URL” 
例如：`http://www.w3school.com.cn:80/html/index.asp`

 - 协议
 包括：http https ws wss ftp sftp rtmp....等等

##### 1） 协议双方 

 - 客户端：发送请求的软件（例如浏览器：谷歌浏览器 火狐浏览器 360 qq 。。。。）

 - 服务端：接收并处理请求的软件（webServer：nginx apache tomcat。。。。）

##### 2） 协议的内容

 - 协议的内容：处理请求的方式

##### 3）域名

		1）服务器 ：一台电脑
		2）IP地址 ：任何一台联网的电脑都有一个IP——在浩瀚的网络中你的电脑的一个唯一标示
		3）IP的别名（域名） ：一般由三段组成（你花钱购买的是“名+后缀”）

##### 4）端口

        1）作用 ：是为一个软件“运行”提供的一个入口
        2）为webServer的运行提供的一个入口
        3）如果你发送的是https请求，那么就会拼接上:443
        4）如果你发送的是http请求，那么就会拼接上:80

##### 5）地址

        1）网络请求的本质是：打开远程电脑中的一个文件，读取其中的内容并返回
        2）你要打开的那个文件的路径：
		        绝对路径：相对于根文件夹而言的路径
		        相对路径：相对于当前文件夹而言的路径
		      参照物：网站根目录（是可以自定义的）

##### 6）参数

访问网页中所需要的一些数据

在URL地址中，`?`后面是参数，多个参数之间用&链接。例如：

https://www.baidu.com:443/s`?`ie=utf-8`&`f=8`&`rsv_bp=1`&`tn=monline_4_dg`&`wd=2325 

### 3.3.5 在自己喜欢的编辑器中修改clone下来的模板并发布

1）打开`Git Bash Here`这个终端输入以下命令，如图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831153221227.png#pic_center)
注意：`ls`是查看当前目录下的文件，当前目录中的`blog`是`clone` 远程仓库时，在项目根目录下创建的文件夹，里面存放有`clone`下来的网站文件。

2）`cd blog` 进入到此文件夹中，如图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831153940401.png#pic_center)

3）由于修改了仓库中的代码，输入 `git status` 点击回车，就可以看到修改过的_comfig.yml文件变成了红色，表示还没有推送到暂存区

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831154611608.png#pic_center)

4）输入以下两行代码你就会发现修改的_comfig.yml文件变成了绿色，这就表示已经推送到了暂存区，但是没有正式提交到本地版本库，如图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831155029361.png#pic_center)

5）执行以下命令提交到本地版本库，如图所示：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831155656489.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

注意：`fourth push` 只是作为此次提交的备注信息，可随便填写！ 
`origin` 是下图图片中所复制的别名（也可以把origin修改成下图复制中的内容）![在这里插入图片描述](https://img-blog.csdnimg.cn/20200831015256649.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center#pic_center)

6）如果你是第一次使用，需运行如下命令

```bash
git config ：当你是第一次安装git，并且第一次提交的时候会提示你执行两行命令。
git config --global user.name "名字" 设置你的名字
git config --global user.email "邮箱" 设置你的邮箱
```

<br>此文章原链接[https://blog.csdn.net/weixin_46323637/article/details/108287483](https://blog.csdn.net/weixin_46323637/article/details/108287483)