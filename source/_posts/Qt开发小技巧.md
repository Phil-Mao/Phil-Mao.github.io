---
title: Qt开发小技巧
date: 2022-03-08 13:26:50
tags:
    - C++ 
    - 经验分享
    - Qt
    - Visual Studio
categories: 编程开发
description: 利用Visual Studio进行C++和Qt开发时遇到的一些错误
---

## Qt
1. 遇到 Qt 报错
```
qt.qpa.plugin: Could not find the Qt platform plugin "windows" in ""
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.
```

使用 qt 自带的`windeployqt.exe` 重新运行一下可执行文件，就OK 啦！
```
windeployqt ./$APP_NAME.exe
```
重新初始化一些qt的依赖库和显示窗口，就完事了。
