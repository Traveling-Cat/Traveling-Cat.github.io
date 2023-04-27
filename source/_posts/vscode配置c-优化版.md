---
title: Vscode配置c++(优化版)
copyright_author: Mario
tags: Vscode
categories: 编程
abbrlink: da63da4c
date: 2023-03-24 10:23:55
updated:
keywords:
description:
top_img:
comments:
cover: https://www.dmoe.cc/random.php?timestamp=37974
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

# 主要步骤

- [vscode](https://code.visualstudio.com/)软件下载

- 安装cpptools工具

- 下载 [MinGW](https://sourceforge.net/projects/mingw-w64/)

- 环境变量的配置

- 简单.cpp文件的运行

  ## Vscode软件下载

  下载链接：[Visual Studio Code ](https://code.visualstudio.com/)

  安装过程可以下一步记住安装的路径

  ## 安装cpptools工具

  ### 安装中文包:

  ![image-20230324102856673](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E5%AE%89%E8%A3%85%E4%B8%AD%E6%96%87%E5%8C%85.png)

### 			安装c/c++语言包:

### 	![image-20230324103154077](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E5%AE%89%E8%A3%85C/C++%E8%AF%AD%E8%A8%80%E5%8C%85.png)

​	  **我在安装的时候是用的：1.8.4，推荐使用该版本。因为该版本.c文件运行之后会产生两个.json文	件，而高版本只会出现一个tasks.json文件**。

![image-20230324103307992](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%94%9F%E6%88%90json.png)

## 下载[MinGW](https://sourceforge.net/projects/mingw-w64/)

MinGW 的全称是：Minimalist GNU on Windows ，实际上是将gcc（c/c++编译器）移植到了 Windows 平台下，并且包含了 Win32API ，因此可以将源代码编译为可在 Windows 中运行的可执行程序。而且还可以使用一些 Windows 不具备的，Linux平台下的开发工具。

选择它的原因：

1. MinGW-w64 是开源软件，可以免费使用。

2. MinGW-w64 由一个活跃的开源社区在持续维护，不会过时。

3. MinGW-w64 支持最新的 C语言 标准。
    使用 Windows 的C语言运行库，因此编译出的程序不需要第三方 DLL ，可以直接在 Windows 下运行。
    总之就是要在windows运行c/c++按就对了。可以理解为c/c++的编译器gcc的windows版

  

**下载解压安装(解压位置最好是某盘根目录)**

​	官方下载网站:[MinGW-w64 - for 32 and 64 bit Windows download | SourceForge.net](https://sourceforge.net/projects/mingw-w64/)

![image-20230324103449295](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E4%B8%8B%E8%BD%BDMinGW01.png)

页面向下拉，找到下一张图的位置

![image-20230324103715177](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E4%B8%8B%E8%BD%BDMinGW02.png)

1. x86_64是指64位的操作系统，i686是指32位的操作系统（别问我为啥不是x32！）

2. win32是开发windows系统程序的协议，posix是其他系统的协议（例如Linux、Unix、Mac OS）

3. 异常处理模型 seh（新的，仅支持64位系统），sjlj （稳定的，64位和32位都支持），  dwarf （优于sjlj的，仅支持32位系统）

4. （谁知道Build revision是干嘛用的，评论区告诉一下，谢谢了） 

   等待下载

   ![image-20230324103947426](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E4%B8%8B%E8%BD%BDMinGW03.png)

​		下载速度较慢

![image-20230324104041212](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E4%B8%8B%E8%BD%BDMinGW04.png)

可以使用123云盘备用链接[MinGW备用链接](https://www.123pan.com/s/oDqA-43Syh.html)

下载完成侯进行解压，解压路径切记记住，最好是某盘的根目录例如下方位置

（文件格式使用.7z格式可以使用[本链接](https://www.123pan.com/s/oDqA-x3Syh.html)下载7z)

![image-20230324104329425](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E4%B8%8B%E8%BD%BDMinGW06.png)

## 环境变量配置

解压完成后进行环境配置以下是win10系统的操作步骤。(操作可能有所差别)

1. **打开系统设置**

![image-20230324104832256](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE1.png)

2. **搜索系统环境变量**

![image-20230324104918012](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE2.png)

3. **增加环境变量**

![image-20230324105024826](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE3.png)

4. **编辑系统环境变量**

![image-20230324105216401](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE4.png)

5. 配置好后别忘了点击 **确认！确认！确认！**

### 验证配置成功

1. **win+r键位打开命令行输入cmd**

![image-20230324105347543](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE6.png)

2. **输入 `gcc -v`**

![image-20230324105505511](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/%E7%8E%AF%E5%A2%83%E9%85%8D%E7%BD%AE7.png)

3. **到此环境配置以及MinGW下载完成。**

## 简单.cpp文件进行运行

1. **建立cpp文件夹**

![image-20230324105822022](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%951.png)   **2. 勾选信任父文件夹**

![image-20230324105916305](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%952.png)

![image-20230324105947708](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%953.png)

3. **新建一个.cpp文件**

```c++
#include <iostream>
using namespace std;
int main()
{
    cout<<"vscode";
    system("pause");
    return 0;
}
```



![image-20230324110340257](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%957.png)



4. **按下F5进行调试，进入调试界面添加配置环境，选择 C++(GDB/LLDB)，再选择 g++.exe，之后会自动生成 launch.json 配置文件**

   ![image-20230324115611766](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/202303241526904.png)

   

5. **编辑 launch.json 配置文件（注意MinGW-gcc的路径）**



6. **如果不生成可以复制下面的内容自己建立一个launch.json**
6. **记得把这个位置的路径修改程自己ming64  gbd.exe的路径**

![image-20230324112044809](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%9510.png)

**编辑launch.json的文件内容**（注意//注释后面的内容）

```json
{
    // 使用 IntelliSense 了解相关属性。 
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [
        {
            "name": "gcc.exe - 生成和调试活动文件",
            "type": "cppdbg",
            "request": "launch",
            "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${fileDirname}",
            "environment": [],
            "externalConsole": false,//flase改成true 此处改为ture可以使用系统终端窗口
            "MIMode": "gdb",
            "miDebuggerPath": "C:\\mingw64\\bin\\gdb.exe",
            "setupCommands": [
                {
                    "description": "为 gdb 启用整齐打印",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                },
                {
                    "description": "将反汇编风格设置为 Intel",
                    "text": "-gdb-set disassembly-flavor intel",
                    "ignoreFailures": true
                }
            ],
            "preLaunchTask": "C/C++: gcc.exe 生成活动文件"
        }
    ]
}
```

8. **修改完成后记得ctrl+s保存。**

**编辑task.json文件**

```json
{
    "tasks": [
        {
            "type": "cppbuild",
            "label": "C/C++: gcc.exe 生成活动文件",
            "command": "C:\\mingw64\\bin\\gcc.exe",
            "args": [
                "-fdiagnostics-color=always",
                "-g",
                "${file}",
                "-o",
                "${fileDirname}\\${fileBasenameNoExtension}.exe",
               //加入这句话 "-fexec-charset=GBK"
            ],
            "options": {
                "cwd": "${fileDirname}"
            },
            "problemMatcher": [
                "$gcc"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            },
            "detail": "调试器生成的任务。"
        }
    ],
    "version": "2.0.0"
}
```

![image-20230324113305314](https://obsidian-1306832247.cos.ap-nanjing.myqcloud.com/blog/cpp%E6%B5%8B%E8%AF%9511.png)

修改完成之后记得ctrl+s保存，再进行运行。

到此vscode -c篇目完成。
