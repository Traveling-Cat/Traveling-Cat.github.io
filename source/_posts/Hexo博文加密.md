---
title: Hexo博文加密
copyright_author: Mario
abbrlink: 15bb51c4
date: 2023-03-28 15:37:14
updated:
tags: 建站
categories: Hexo
keywords:
description:
top_img:
comments:
cover: https://api.ucany.net/acg-pc.php?timestamp=188
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author_href:
copyright_url:
copyright_info:
mathjax:
katex:
aplayer:
highlight_shrink:
aside:
---

# 一、概述

1. Hexo文章内容加密的方式有很多，一般是使用可逆的加密算法对文章内容进行加密解密，比如可以使用”AES加密算法”等，当然也可以自己编写一些算法，总之保持加密后的字符串可逆即可。在前端，将字符串解密之后，添加相关的样式就可以展示出来了。Hexo现在也有相关的插件，例如Hexo-Blog-Encrypt，hexo-encrypt。这些插件使用起来非常方便，安装之后简单的配置一下就可以使用。我的博客使用的是Hexo-Blog-Encrypt。

2)　Hexo可以运行在众多的服务器软件上面，例如有：Nginx，Tomcat，Apache等。这些软件基本上也都提供了路径访问控制的功能。本网站使用的是Nginx，因此就需要采用Nginx的授权访问控制功能。

# 二、前端加密方式

　　前端加密方式，就是对文章的内容进行加密解密，这个是实现的原理也很简单，如果对前端比较了解的话，也可以自己写一个这样的加密插件。比较知名的加密插件有Hexo-Blog-Encrypt，hexo-encrypt等。经过比较，最终使用了Hexo-Blog-Encrypt插件，已开源，github地址为[Hexo-Blog-Encrypt](https://github.com/MikeCoder/hexo-blog-encrypt)

## 安装配置 

hexo安装插件的方式有两种，一种是在package.json中写入所需要的的插件名，然后npm install，另一种方式是直接使用 npm install –-save  <插件名>即可。 这里选用后者进行安装：

`npm install –-save hexo-blog-encrypt`

## 使用

在需要加密的文章头部添加所要求的字段，如：password，abstract，message等。

```
---
title: 文章加密
date: 2023-03-28 15:37:14
password: 人间草木
abstract: 这是一篇加密博文，请输入密码后查看
message: 这里需要密码才能访问.
wrong_pass_message: 抱歉, 这个密码看着不太对, 请再试试.
---
```

## 注意点

1. 尽量使用最新版本的插件，因为之前的版本对一些特性的支持可能不是很好。
2. 如果你的博客使用了TOC，这就要进行一些额外的处理，不同的主题处理方式不一样，这个网上有教程。
3. 部分博客中, 解密后部分元素可能无法正常显示或者表现, 这属于已知问题. 目前的解决办法是通过自行查阅自己的博客中的代码, 了解到在 onload 事件发生时调用了哪些函数, 并将这些函数挑选后写入到博客内容中。
