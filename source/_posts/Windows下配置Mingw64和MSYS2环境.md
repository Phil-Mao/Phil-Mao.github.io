---
title: Windows下配置Mingw64和MSYS2环境
date: 2022-03-08 13:27:22
tags:
    - 经验分享
    - Windows
    - Mingw
    - MSYS2
categories: 编程开发
description: MSYS2是一组工具和库，提供一个易于使用的环境，用于构建、安装和运行本地 Windows 软件。
---

##  下载MSYS2

MSYS2是一组工具和库，提供一个易于使用的环境，用于构建、安装和运行本地 Windows 软件。下载地址：[MSYS2 latest 下载地址](https://www.msys2.org/)

## 安装

官网有详细的安装步骤，这里不再赘述，参考[安装手册](https://www.msys2.org/)
 
##  更换国内镜像源
在安装新包之前，建议把MSYS2使用的镜像源换成国内源。默认路径安装的话，需要修改的文件在 `C:\msys64\etc\pacman.d` 文件夹内，把`mirrorlist.clang32`、`mirrorlist.clang64` 等7个文件进行如下修改：
![修改前](https://img-blog.csdnimg.cn/cb5f817ca63c4a16b3dea6f87e44d50d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_20,color_FFFFFF,t_70,g_se,x_16)

![修改后](https://img-blog.csdnimg.cn/e716e870e2c04e9e9f389651f9ba8763.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_20,color_FFFFFF,t_70,g_se,x_16)


## 安装新库

接着就是按照编译的需要，安装相应的库文件
```
@REM Make sure start with ucrt64 msys2 environment
pacman -Syu 
pacman -S mingw-w64-ucrt-x86_64-cmake --needed
```

安装新包时，选择带`ucrt`的包进行安装

>ucrt64：Visual Studio的新宠，全名是Universal C Runtime，用来替代前面mingw64&w32里的msvcrt。ucrt不支持加载msvcrt的产物，因此老版本Windows（<10）不能直接兼容基于它的软件。但是这不是无理由的激进，要知道msvcrt在当前开发环境里真的是让开发打哑谜，（原生）不支持C99，不支持UTF8
