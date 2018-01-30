---
layout: post
title: How To Start Jekyll
date: 2018-01-29 22:10:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: how-to-start.jpg # Add image post (optional)
tags: [blog, jekyll, Learn] # add tag
---

# 第一步，创建项目。 #

在你的电脑上，建立一个目录，作为项目的主目录。我们假定，它的名称为jekyll_demo。

　　$ mkdir jekyll_demo

对该目录进行git初始化。

>　 $ cd jekyll_demo  
>　 $ git init

然后，创建一个没有父节点的分支gh-pages。因为github规定，只有该分支中的页面，才会生成网页文件。

　　$ git checkout --orphan gh-pages

以下所有动作，都在该分支下完成。

# 第二步，创建设置文件。 #

在项目根目录下，建立一个名为_config.yml的文本文件。它是jekyll的设置文件，我们在里面填入如下内容，其他设置都可以用默认选项，具体解释参见官方网页。

　　baseurl: /jekyll_demo

目录结构变成：

>　　/jekyll_demo  
>　　  |--　_config.yml

# 第三步，创建模板文件。 #

在项目根目录下，创建一个_layouts目录，用于存放模板文件。

　　$ mkdir _layouts

进入该目录，创建一个default.html文件，作为Blog的默认模板。并在该文件中填入以下内容。  
```
>　　`<!DOCTYPE html>`  
>　　`<html>`  
>　　`<head>`  
>　　　`<meta http-equiv="content-type" content="text/html; charset=utf-8" />`  
>　　　`<title>{{ page.title }}</title>`  
>　　`</head>`  
>　　`<body>`  
>　　`{{c o n t e n t}}`  
>　　`</body>`  
>　　`</html>`

Jekyll使用Liquid模板语言，`{{page.title}}`(单引号内为双层大括号中的page.title)表示文章标题，`{{c o n t e n t}}`(单引号内为双层大括号中的content)表示文章内容，更多模板变量请参考官方文档。
目录结构变成：
```
>　　/jekyll_demo  
>　　 　|--　_config.yml  
>　　 　|--　_layouts  
>　　 　|　　　|--　default.html  


# 第四步，创建文章。 #

回到项目根目录，创建一个_posts目录，用于存放blog文章。

　　$ mkdir _posts

进入该目录，创建第一篇文章。文章就是普通的文本文件，文件名假定为2012-08-25-hello-world.html。(注意，文件名必须为"年-月-日-文章标题.后缀名"的格式。如果网页代码采用html格式，后缀名为html；如果采用markdown格式，后缀名为md。）
在该文件中，填入以下内容：（注意，行首不能有空格） 


>　见阮一峰的原文。　

 
有了文章以后，还需要有一个首页。
回到根目录，创建一个index.html文件，填入以下内容。


>　见阮一峰的原文。



它的Yaml文件头表示，首页使用default模板，标题为"我的Blog"。然后，首页使用了（两边大括号加百分号，中间套post相关内容），表示对所有帖子进行一个遍历。这里要注意的是，Liquid模板语言规定，输出内容使用两层大括号，单纯的命令使用一层大括号。至于site.baseurl就是_config.yml中设置的baseurl变量。
目录结构变成：

>　　/jekyll_demo    
>　　 　|--　_config.yml    
>　　 　|--　_layouts    
>　　 　|　　　|--　default.html    
>　　 　|--　_posts      
>　　 　|　　　|--　2012-08-25-hello-world.html      
>　　 　|--　index.html  

# 第六步，发布内容。#

现在，这个简单的Blog就可以发布了。先把所有内容加入本地git库。

>　　$ git add .  
>　　$ git commit -m "first post"

然后，前往github的网站，在网站上创建一个名为jekyll_demo的库。接着，再将本地内容推送到github上你刚创建的库。注意，下面命令中的username，要替换成你的username。

>　　$ git remote add origin https://github.com/username/jekyll_demo.git  
>　　$ git push origin gh-pages

上传成功之后，等10分钟左右，访问http://username.github.com/jekyll_demo/(com应为io)就可以看到Blog已经生成了（将username换成你的用户名）。

# 第七步，绑定域名。 #

如果你不想用http://username.github.com/jekyll_demo/(com应为io)这个域名，可以换成自己的域名。
具体方法是在repo的根目录下面，新建一个名为CNAME的文本文件，里面写入你要绑定的域名，比如example.com或者xxx.example.com。
如果绑定的是顶级域名，则DNS要新建一条A记录，指向204.232.175.78。如果绑定的是二级域名，则DNS要新建一条CNAME记录，指向username.github.com（请将username换成你的用户名）。此外，别忘了将_config.yml文件中的baseurl改成根目录"/"。
至此，最简单的Blog就算搭建完成了。进一步的完善，请参考Jekyll创始人的示例库，以及其他用Jekyll搭建的blog。

# 说明 #

本文转自阮一峰的“搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门”。

亲测可用，但第七步未实施。后来我根据这个利用jekyll theme模板“flexible-jekyll”建立了我的博客。上传时出现了问题，提示如下：

fatal: remote origin already exists.

先输入$ git remote rm origin  
再输入$ git remote add origin https://github.com/username/flexible-jekyll.git

成功建立了我的第一个jeyll博客。