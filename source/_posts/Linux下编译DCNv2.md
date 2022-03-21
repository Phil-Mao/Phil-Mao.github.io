---
title: Linux下编译DCNv2
date: 2022-03-08 13:26:02
tags:
    - 经验分享
    - Linux
    - C++
    - DCN
    - Conda
categories: 编程开发
description: 最近需要编译一下DCN这个网络，使用conda管理依赖库是真的方便，需要的东西往里放，只要版本之间不冲突，对编译代码十分友好。
---

最近需要编译一下DCN这个网络，使用`conda` 管理依赖库是真的方便，需要的东西往里放，只要版本之间不冲突，对编译代码十分友好。
# 配置
```
GPU：RTX 3080
系统： Linux Mint 20.1 Cinnamon 4.8.6
Cuda: 11.1
Pytorch: 1.8.1
```
# 运行环境
根据需要的依赖库下载对应的conda环境，这里提供我自己使用的conda 环境下载地址，其实有很多依赖库是用不着的：
`
https://github.com/Phil-Mao/AnacondaRecipies/tree/master/_environments
`
Clone之后，创建一个conda环境：
```
conda env create -n mvs -f _environments/mvs.fixed.yml
```
激活`mvs`环境，`conda activate mvs`:
![激活mvs](https://img-blog.csdnimg.cn/727d92022b3541bd9d52b998f174532a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_20,color_FFFFFF,t_70,g_se,x_16)
# DCNv2-latest
这里我用的是一个比较新的版本：
[https://github.com/jinfagang/DCNv2_latest](https://github.com/jinfagang/DCNv2_latest)

# 编译
这里需要指定`cuda`对应版本安装的位置：
```
set CUDA_HOME=/usr/local/cuda-11.1
```
一键编译：
```
python setup.py build develop
```
![compile](https://img-blog.csdnimg.cn/c6554a0bc99c4a0c94e2fb9e9de4880a.png)
编译成功：
![end](https://img-blog.csdnimg.cn/2e522537473c4acea0607e9bfdb3ae87.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_20,color_FFFFFF,t_70,g_se,x_16)
编译后生成的文件：
![编译完成](https://img-blog.csdnimg.cn/786eb166867e464e9dc69963c0ec2d46.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_19,color_FFFFFF,t_70,g_se,x_16)
build完之后，目前只是在当前文件夹下有.so文件，现在我们需要把他装载到我们的环境里面，这里直接运行
```
python setup.py install
```
在当前的`conda`环境里进行第三方库的安装：
![安装到虚拟环境中](https://img-blog.csdnimg.cn/050642bff12446f99a5d065898f52e96.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBAQml0X0xlZw==,size_20,color_FFFFFF,t_70,g_se,x_16)
可以看到编译好的`DCNv2`被安装在了 `conda` 环境下的包管理目录下，激活环境：
![成功安装](https://img-blog.csdnimg.cn/13c6a6fb8fe54f87a3f5e1b27c2be010.png)
至此，`DCNv2`的编译和安装就已经完成了。