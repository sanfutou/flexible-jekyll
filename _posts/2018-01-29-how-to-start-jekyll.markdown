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

在项目根目录下，创建一个_layouts目录，用于存放模板文件。

　　$ mkdir _layouts

进入该目录，创建一个default.html文件，作为Blog的默认模板。并在该文件中填入以下内容。


Jekyll使用Liquid模板语言，`{{page.title}}`表示文章标题，`{{con tent}}`表示文章内容，更多模板变量请参考官方文档。
目录结构变成：

　　/jekyll_demo
　　　　|--　_config.yml
　　　　|--　_layouts
　　　　|　　　|--　default.html

# 第四步，创建文章。 #

回到项目根目录，创建一个_posts目录，用于存放blog文章。

　　$ mkdir _posts

进入该目录，创建第一篇文章。文章就是普通的文本文件，文件名假定为2012-08-25-hello-world.html。(注意，文件名必须为"年-月-日-文章标题.后缀名"的格式。如果网页代码采用html格式，后缀名为html；如果采用markdown格式，后缀名为md。）
在该文件中，填入以下内容：（注意，行首不能有空格）