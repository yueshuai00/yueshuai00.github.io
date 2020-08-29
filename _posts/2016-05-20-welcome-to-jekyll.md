---
layout: page
title:  "如何使用GitHub创建一个属于自己的博客（一）"
subtitle: "如何使用GitHub创建一个属于自己的博客（一）"
date:   2020-08-29 21:21:21 +0530
categories: [""]
---
# 一、Git是什么
Git，全称是分布式版本控制系统,可以有效、高速的处理从很小到非常大的项目版本管理。<br>每个开发者可以通过克隆**git clone**,在本地机器上拷贝一个完整的**Git**仓库。
# 二、安装Git
- 点击此链接[Git官网](https://git-scm.com/)进入到Git官网下载并且安装Git
- 点击Downloads选择你所需要的版本进行下载
![Git下载图片](https://img-blog.csdnimg.cn/20200828210639732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
- 下载安装之后，你会在任意一个文件夹中点击右键均可看到"**git bash here**"这个命令行工具
![图片](https://img-blog.csdnimg.cn/20200828210932769.png#pic_center)
## 如何开始使用Git这个终端呢
- 打开**git bash here** 这个终端后有个命令叫**git init**（初始化本地仓库-本质）：会在你的项目根目录中新建一个隐藏文件夹(.git)
<br> **注：如果项目中有.git这个文件夹就不需要我们手动去初始化**

## 本地代码如何提交到远程网站中
- git add . (将本地代码推到本地代码中的暂存区)
- git commit -m "提交信息" （将暂存区中的代码正式提交到本地版本库）
- git push 远程地址 本地分支名:远程分支名 （将本地版本库中的代码提交到远程版本库）
## 远程的代码如何下载/合并到本地中
- **git clone -b 远程分支名 远程地址** 当你本地还没有项目代码的时候，需要完整的下载一个远程项目，需要用到此命令<br>（如果不加-**b**也就是不指定哪个分支，会默认**master**分支）
- **git merge 指定远程分支** 合并某个拉取下来的分支中的代码
- **git fetch** 拉取远程版本库中所有有变化的分支中的内容
## 本地如何进行分支管理
- **git branch** 查看本地有哪些分支
- **git checkout 分支名** 切换分支
- **git branch 分支名** 新建分支
# 三、注册一个GitHub账号
打开[GitHub官网](http://github.com)
[注册界面](https://img-blog.csdnimg.cn/20200828213412993.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
## 配置SSH公钥
**作用：为了免密码登陆，但也得需要一个“凭证”（电脑凭证：指代你的这台正在使用的电脑）在命令行中输入以下命令**
1. 首先查看你的电脑中是否有这个凭证
>cat ~/.ssh/id_rsa.pub
2. 生成该凭证
>ssh-keygen -t rsa -C "输入你的邮箱
3. 生成之后获取凭证
>cat ~/.ssh/id_rsa.pub
4. 把生成的凭证添加到**GitHub**里面
[添加界面](https://img-blog.csdnimg.cn/202008291415018.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
# 四、GitHub Pages
**GitHub这个网站中的一些功能**
1. 让一个小白能够快速的认知代码，感受到代码给你带来的快乐
2. 程序员的福利-用最简单的语言上线自己的一个项目
3. 它提供了我们一个域名，**GitHub**的服务器中的一部分空间
## 博客页面的一个主题网站
1. [http://jekyllthemes.org](http://jekyllthemes.org)
2.  进去之后呢选择一个主题点击**homepage**这个按钮（这是点击了homepage进去之后显示的界面）
[图片](https://img-blog.csdnimg.cn/20200829144259225.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
3. 接下来点击以上图片中右上角的那个**fork**按钮（把这个项目复制到我们自己的仓库中来）
[图片](https://img-blog.csdnimg.cn/20200829155339497.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
4. **fork**过来之后需要点击**Settings**这个按钮把仓库名字改成你自己的**用户名.github.io**
[图片](https://img-blog.csdnimg.cn/20200829155554673.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
# 五、把远程仓库代码克隆到本地
1. 复制SSH里面的链接
[图片](https://img-blog.csdnimg.cn/20200829161945636.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
2.在我们的项目根目录中打开命令行工具**Git Bash Here**执行一句话 
[图片](https://img-blog.csdnimg.cn/20200829162026258.png#pic_center)

<br>以上步骤呢是已经创建好了自己的博客项目远程版本库了

<br>此文章原链接[https://editor.csdn.net/md/?articleId=108287483#Git_7](https://editor.csdn.net/md/?articleId=108287483#Git_7)