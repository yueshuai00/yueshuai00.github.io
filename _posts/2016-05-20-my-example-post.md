---
layout: page
title:  "上线博客（二）"
subtitle: "上线博客（二）"
date:   2020-08-29 21:21:21 +0530
categories: [""]
---

# 四、用Docker搭建服务器

## 4.1 购买服务器及域名

 - 系统选择
      
	- Windows
    - linux
    - ubuntu （推荐）
    - Mac

 - 工具选择
    - **Xshell**：用来登陆远程服务器 用终端控制远程服务器
    - **Xftp** ：向远程服务器传文件

本实例采用阿里云介绍，阿里云官方地址（[https://www.aliyun.com/](https://www.aliyun.com/)）

1. 首先注册一个阿里云账号（如有：请跳过）

2. 登录后选择**云服务器ECS**：请看下图:

![https://img-blog.csdnimg.cn/20200904211226947.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904211226947.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

点击后进入购买界面，如图所示：

![https://img-blog.csdnimg.cn/20200904211431866.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904211431866.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

2.1 点击购买，跳转页面如图所示:

![https://img-blog.csdnimg.cn/20200904212755807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904212755807.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
![https://img-blog.csdnimg.cn/20200904213344927.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904213344927.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

 2.2 配置好了之后点击下一步，如图：

 ![https://img-blog.csdnimg.cn/20200904213934354.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904213934354.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
![https://img-blog.csdnimg.cn/20200904214217915.png#pic_center](https://img-blog.csdnimg.cn/20200904214217915.png#pic_center)

2.3 配置好了在点击下一步，如图：

![https://img-blog.csdnimg.cn/20200904214647377.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904214647377.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
![https://img-blog.csdnimg.cn/20200904214911451.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904214911451.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

2.4 配置好了点击下一步，如图：

![https://img-blog.csdnimg.cn/20200904215321476.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904215321476.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

**到了这一步点击确认订单，购买**（接下来进入到控制台界面就可以看到你所购买的服务器了）

记录下IP(公网)，打开Xshell，连接到服务器。

## 4.2 购买域名（略，不懂自行百度）

## 4.3 远程连接服务器

 1. 打开Xshell新建一个会话

 ![https://img-blog.csdnimg.cn/20200904220744533.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904220744533.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

  2. 属性面板配置

  ![https://img-blog.csdnimg.cn/20200904221715824.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center](https://img-blog.csdnimg.cn/20200904221715824.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

  输入cd / 进入根目录，键入 ls（查看命令）可以看到当前目录下的文件列表。cd + ls 配合使用相当于windows的双击。

```bash
 cd /

```

![https://img-blog.csdnimg.cn/20200904222319931.png#pic_center](https://img-blog.csdnimg.cn/20200904222319931.png#pic_center)

这样就能看到Ubantu系统的所有文件夹。再次输入cd ，回到购买登录时的位置

### 4.3.1 使用Docker搭建环境

博客是一个纯粹静态网页，想把博客放上去运行，只需要WebServer就可以实现需求。这里我们采用Docker

**1)** 修改镜像源
进入[阿里云镜像网站](https://developer.aliyun.com/mirror/)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904223140495.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

**2）** 备份镜像源文件

终端中输入命令如下：

```bash
mv /etc/apt/sources.list /etc/apt/sources.list.bak

```

**3）** 新建镜像源文件

输入以下命令进入编辑器，然后按`a`键进入编辑模式。接着复制阿里云官方**ubuntu16.04**的配置，并粘贴到 **vim**编辑器中。

```bash
vim /etc/apt/sources.list

```
		
Ubuntu 16.04配置如下：

```bash
deb http://mirrors.aliyun.com/ubuntu/ xenial main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main

deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main

deb http://mirrors.aliyun.com/ubuntu/ xenial universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates universe

deb http://mirrors.aliyun.com/ubuntu/ xenial-security main
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main
deb http://mirrors.aliyun.com/ubuntu/ xenial-security universe
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security universe

```

键盘上按`ESC`，退出编辑模式，再在命令行输入`:wq`，敲回车保存修改。

**4）** 更新源信息

键入以下命令：

```bash
apt-get update

```

如图：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904224237179.png#pic_center)

**5）** **ubuntu 16.04** 安装`docker` 以及`docker-compose`

安装Docker：

```bash
apt-get install docker.io

```

**注：出现提示，敲Y后回车开始安装**

查看安装是否成功：
		
```bash
docker -v 或 docker -version

```

回车运行后出现版本号即为成功

```bash
在linux系统中如何查看某个软件是否安装成功
该软件名（命令名） -v 或者 软件名（命令名） --version
出现版本号 即为安装成功

```

**6）** 更换Docker镜像源

 - 访问[https://cr.console.aliyun.com/cn-beijing/instances/mirrors](https://cr.console.aliyun.com/cn-beijing/instances/mirrors)
 
 - 按照文档中的操作逐步进行

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904230026670.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

（1）

```bash
sudo mkdir -p /etc/docker

```
（2）

```bash
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://q829bswc.mirror.aliyuncs.com"]
}
EOF

```

（3）

```bash
sudo systemctl daemon-reload

```

（4）

```bash
sudo systemctl restart docker

```

**执行完毕即完成了镜像源更换。**

**7）** 安装docker-compose

安装命令：

```bash
sudo curl -L "https://get.daocloud.io/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```

给**docker-compose**添加一个执行权限

```bash
chmod +x /usr/local/bin/docker-compose

```

将课件中的docker文件夹 拖拽到服务器中的家目录（你一开始进入服务器时所在的文件夹）

说明：上传前，请将docker\phpdocker\nginx下的nginx.conf文件修改为正确的域名，如下图：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904231611128.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)
查看docker-compose是否安装成功

```bash
docker-compose -v

```

**出现版本号即为成功**

**8）**  安装nginx 搭建环境

在Xshell中键入命令：

```bash
// 进入docker文件夹
cd docker

```

执行 `docker-compose up -d` 命令 启动docker

### 4.3.2 上线博客

- 在你本机安装ruby（ruby下载链接：[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)）
    - 在本机终端 敲击 `gem install jekyll`(大概5分钟左右)
    - 在本机终端敲击`jekyll -v` 出现版本号即为成功
    - 在项目根目录中 `jekyll build` 就会出现_site

**选择2.6版本，下载后直接安装，并在本机运行cmd 命令行工具，输入如下命令：**

```bash
gem install jekyll

```

查看是否安装成功：

```bash
jekyll -v

```

打开 `Git Bash Here` 进入到blog项目文件夹，执行项目打包：

```bash
jekyll build

```

**用`ls`查看项目文件夹，会发现多了一个`_site`文件夹（这个文件夹里的所有文件就是要放到网站上的文件）。然后用Xftp将文件上传到服务器。**

### 4.3.3 上传网站
（1）
逐级点开文件夹：/root/docker/www/blog
即：把文件放到docker文件夹下面的www文件夹下的blog文件夹里。

（2）
删除原有的html测试文件。将左边本地的文件全部选中拖拽到右侧服务器blog文件夹下(稍等即上传成功)


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904233250196.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)

### 4.3.5 访问博客

如果没有域名，可直接用IP地址访问

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200904233805897.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMyMzYzNw==,size_16,color_FFFFFF,t_70#pic_center)