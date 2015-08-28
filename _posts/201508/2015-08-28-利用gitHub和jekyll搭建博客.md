---
layout: page
title: 如何利用gitHub搭建博客
tagline: Supporting tagline
---
{% include JB/setup %}


##1、gitHub Page的的使用

我觉得这边博文写的很清楚，方法、步骤、优缺点以及实例，所以就借用一下啦^_^
[搭建一个免费的，无限流量的Blog](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)

不过按照文章中的实例生成出来的博客基本是无法使用的，要想更简单快捷的生成有逼格的博客，可以参考第2点.
 
##2、利用jekyll写博客

进入[The Quickest Way to Blog on GitHub Pages](http://jekyllbootstrap.com/)可以整体了解一下gitHub如何使用jekyll的

点击[0 to Blog in 3 Minutes](http://jekyllbootstrap.com/usage/jekyll-quick-start.html) 开始博客创建之旅

 2.1、Host on GitHub in 3 Minutes

文章写的很清楚，执行完前面3步自己的博客就算生成好了，而且也有一定的逼格^_^.

 2.2、 Run Jekyll Locally

在本地运行jekyll我自己还没有尝试过，感兴趣的可以自己试试,我在Linux上使用，到目前为止就可以了.

 2.3、Create a Post

因为在第2步的时候没有在本地安装Jekyll，后面的几个步骤我就写一下我自己是怎么操作的，如果安装了的就直接按照文档上操作就可以了，上面的英语简单易懂^_^.

直接在_posts目录下创建文件夹如core-samples(名字任意，主要是是方便分类,这个是自带的例子)，然后创建以日期为首的文件2011-12-29-jekyll-introduction.md

 2.4、Create a Page


 2.5、Publish

就是

git commit

git push 

把更新的文件提交到gitHub上即可,具体的可以参考git的使用方法.

 2.6、Customize

让自己的博客看起来更有逼格更个性化一些，jekyll自己准备了几个主题，可以按照上面的方式自己更换，如果自己会点css那就更好了^_^.

我写一下自己更换的方式，跟文档上面不太一样:

  2.6.1)、找主题，这一步跟官网一样访问[Theme Explorer](http://themes.jekyllbootstrap.com/)

  2.6.2) 、相中合适的主题之后点击 Install Theme 会弹出一个安装方法的弹层，我们只需要那个git地址，将它拷贝到本地时使用，例如我自己使用的这个主题：

	git clone git://github.com/jekyllbootstrap/theme-mark-reid.git

  2.6.3) 、手动将主题文件下的assets、_includes 拷贝到自己博客对应的目录下，在项目中保持跟下载下来的目录一致。

  2.6.4)、更改_layout目录下所有文件的主题名称、include的目录中与主题相关的内容

	theme :
	
	name : mark-reid
	
	......

	"{" % include themes/mark-reid/page.html % "}"
	
	......

  2.6.5) 、 找一些颜色搭配比较好看的博客/网站，更改一下自己的css文件。
