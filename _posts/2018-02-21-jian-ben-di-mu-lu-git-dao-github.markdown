---
layout: post
title: 如何将一个已存在的目录转换为一个 GIT 项目并托管到 GITHUB 仓库
date: 2018-02-21 21:28:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: how-to-start.jpg # Add image post (optional)
tags: [git, github, Learn] # add tag
---

本文只讲一件事：将一个本地维护的项目，转换为一个 Git 项目，并托管到 GitHub。  


总共以下几个步骤：  


##一、 打开命令行终端，进入项目所在的本地目录，将目录初始化为一个 Git 项目  


$ git init  

此时会在目录中创建一个 .git 隐藏文件夹  


##二、 将所有文件放进新的本地 git 仓库  


$ git add .  

如果你本地已经有 .gitignore 文件，会按照已有规则过滤不需要添加的文件。如果不想要添加所有文件，可以把 . 符号换成具体的文件名  


##三、 将添加的文件提交到仓库  


$ git commit -m "Initial commit"  

##四、 访问 GitHub  


有些时候可能要翻墙(实际不需要）  


##五、 创建一个新仓库  


为了避免冲突，先不要勾选 README 和 LICENSE 选项  


##六、 在生成的项目主页上，复制仓库地址  


类似于 https://github.com/superRaytin/alipay-app-ui.git  


##七、 回到命令行终端界面，将本地仓库关联到远程仓库  


$ git remote add origin https://github.com/superRaytin/alipay-app-ui.git  

可运行以下命令查看结果：  


$ git remote -v  

##八、 提交代码到 GitHub 仓库  


$ git push origin master  
  
进行了试用，但是最后一步时上传不成功。似乎与网络的状态有关。
2018.2.24我重新建立了一个空目录试了下，成功。看来主要是文件太多，网络支持不够造成的。  
 
上传成功后，在github本地桌面中没有见到这个仓库，通过运行桌面github程序，直接点+号，增加一个仓库，将已经关联的仓库管理起来，见图。

![]({{site.baseurl}}/assets/img/2018-2-24 10-04-44.jpg)
  

