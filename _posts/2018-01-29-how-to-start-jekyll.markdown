---
layout: post
title: How To Start Jekyll
date: 2018-01-29 22:10:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: how-to-start.jpg # Add image post (optional)
tags: [Programming, Learn] # add tag
---

# 第一步，创建项目。 #

在你的电脑上，建立一个目录，作为项目的主目录。我们假定，它的名称为jekyll_demo。

　　$ mkdir jekyll_demo

对该目录进行git初始化。

　　$ cd jekyll_demo
　　$ git init

然后，创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件。

　　$ git checkout --orphan gh-pages

以下所有动作，都在该分支下完成。

# 第二步，创建设置文件。 #

在项目根目录下，建立一个名为_config.yml的文本文件。它是jekyll的设置文件，我们在里面填入如下内容，其他设置都可以用默认选项，具体解释参见官方网页。

　　baseurl: /jekyll_demo

目录结构变成：

　　/jekyll_demo
　　　　|--　_config.yml

# 第三步，创建模板文件。 #

