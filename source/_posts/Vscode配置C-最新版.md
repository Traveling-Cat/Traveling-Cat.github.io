---
title: Vscode配置C++(最新版)
copyright_author: Mario
theme: xray
password: ''
abstract: 〒▽〒 有什么东西被加密了
message: w(ﾟДﾟ)w 这里竟然需要密码
wrong_pass_message: (ˉ▽￣～) 切~~
tags: Vscode
categories: 编程
abbrlink: 6cac8be1
date: 2023-03-30 11:13:46
updated:
keywords:
description:
top_img:
comments:
cover: https://api.ucany.net/acg-pc.php?timestamp=134967
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
sticky:
---

# 							VSCode配置C/C++环境

2023-03-29日测试配置环境，运行状态良好。

本文借鉴csdn大神分享的[Vscode配置C/C++环境](https://blog.csdn.net/Hudiscount/article/details/120209994)以及[VSCode配置C/C++环境 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/87864677)

## VSCode简介

VSCode是一款微软出的轻量级编辑器，它本身只是一款文本编辑器而已，所有的功能都是以插件扩展的形式所存在，想用什么功能就安装对应的扩展即可，非常方便，同时也支持非常多的主题和图标，外观比较好看，重要的是VSCode支持各大主流操作系统，包括Windows、Linux和Mac OS。所以就选择它作为自己的一款主要的编辑器来使用。

## 一、下载

## 二、安装

## 三、设置中文环境

## 四、完全卸载

## 五、配置C/C++环境

1. 官网下载[MinGW](https://sourceforge.net/projects/mingw-w64/files/mingw-w64/)编译器(一定要记得mingw的安装路径，能打开所在的文件夹)

​	补充[网盘链接](https://www.123pan.com/s/oDqA-LHSyh.html)

​	![image-20230329183225529](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/202303301114348.png)

​	下滑找到如图所示位置

![image-20230329183408507](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/202303301114282.png)

​	

- x86_64是指64位的操作系统，i686是指32位的操作系统（别问我为啥不是x32！）
- win32是开发windows系统程序的协议，posix是其他系统的协议（例如Linux、Unix、Mac OS）

​		异常处理模型 seh（新的，仅支持64位系统），sjlj （稳定的，64位和32位都支持），  dwarf (优		于sjlj的，仅支持32位系统）

​	谁知道Build revision是干嘛用的，评论区告诉一下，谢谢了

​	等待下载

![image-20230329183452125](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/202303301114633.png)

​	
