---
title: Markdown基本用法
date: 2022-03-10 09:51:57
tags:
    - 经验分享
    - Markdown
    - 论文写作
categories: 常用工具
description: Markdown是一种轻量级的标记语言，可以用它来给纯文本文件添加格式化元素。
---
<!-- <script src="https://cdn.bootcdn.net/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML"></script> -->
Markdown是一种轻量级的标记语言，可以用它来给纯文本文件添加格式化元素。
## 文本样式
- 斜体
    - 使用下划线(`_`)包裹文本，例如，`_斜体_`效果就是 _斜体_
- 加粗
    - 使用两个星号(`**`)或者两个下划线(`__`)包裹文本，例如，`**加粗**`效果就是 **加粗**，两个下划线`__加粗__`效果就是 __加粗__
- 删除文本
    - 使用两个波浪号(`~~`)包裹文本，例如，`~~删除文本~~`效果就是 ~~删除文本~~

## 标题
- 一级标题
    - 使用一个井号(`#`)，例如，`# 一级标题`
    # 一级标题
- 二级标题，即使用两个井号，以此类推
    - 使用两个井号(`##`)，例如，`## 二级标题`
    ## 二级标题

## 超链接
- 内联链接

需要将被链接的文本用方括号(`[]`)包裹起来， 然后将链接地址用圆括号(`()`)包裹起来，例如，`[github](https://github.com/)`就是链接到 [github](https://github.com/)

- 全局链接

链接到文档的另外一个位置，例如链接到[谷歌搜索](https://www.google.com/?hl=zh_CN)

## 图片
- 内联图片链接
    - 创建一个内联的图片链接， 需要输入一个感叹号(`!`)将方括号(`[]`)中的描述性文本包裹起来， 然后使用圆括号(`()`)包裹链接地址。例如`![avatar](/images/apple-touch-icon.png)`，效果就是![avator](/images/apple-touch-icon.png)
- 全局图片链接
    - 和`全局链接`相似，同样
```
    ![SWJTU_logo][swjtu]
    [swjtu]:https://www.swjtu.edu.cn/images/logob.png
```

效果就是![SWJTU_logo][swjtu]

[swjtu]:https://www.swjtu.edu.cn/images/logob.png

## 引用块
- 在引用文本首行添加(`<`)。例如`>爱我所爱，行我所行，听从我心，无问西东`，效果就是 
> 爱我所爱，行我所行，听从我心，无问西东

## 列表
- 无序列表
    - 在每一个列表项前加一个(`*`)或者短横线(`-`)或者加号(`+`),例如`- 短横线` `* 星号` `+ 加号`，效果就是
- 短横线
    * 星号
        + 加号
---
- 有序列表
    - 在每一个列表项前加数字,例如`1. 第一项`,效果就是
1. 第一项
2. 第二项  
>**使用`Tab`键进行文本的缩进**  


## 段落
- 使用两个连续空格进行分段，效果就是    
> 真正高明的人，  
就是能够借助别人的智慧，  
来使自己不受蒙蔽

## 表格
- 使用(`|`)进行表格内容划分，使用(`-`)来分隔表头和其他行，例如  
    ```
    |  表头   | 表头  |
    |  ----  | ----  |
    | 单元格  | 单元格 |
    | 单元格  | 单元格 |
    ```
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |  

- 设置表格的对齐方式：
    - `-:`设置内容和标题栏居右对齐
    - `:-`设置内容和标题栏居左对齐
    - `:-:`设置内容和标题栏居中对齐    

例如,
```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 留守猿 | 王祥 | 马超 |
| 阿理尬豆 | 李狗蛋 | 张晓松 |
```
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 留守猿 | 王祥 | 马超 |
| 阿理尬豆 | 李狗蛋 | 张晓松 |

## LaTeX数学公式
- 使用LaTeX数学公式，[参考网址](https://katex.org/docs/api.html)  
Gamma公式展示 
![](https://gitee.com/maoshunfu/blogimages/raw/master/img/latex.png)


## 制图-Mermaid
- 插入甘特图，[参考网址](https://mermaid-js.github.io/mermaid/#/gantt)   

![](https://gitee.com/maoshunfu/blogimages/raw/master/img/gantt.png)


- 插入UML图，[参考网址](https://mermaid-js.github.io/mermaid/#/sequenceDiagram)

![](https://gitee.com/maoshunfu/blogimages/raw/master/img/uml.png)

- 插入流程图，[参考网址](https://mermaid-js.github.io/mermaid/#/flowchart?id=graph)

![](https://gitee.com/maoshunfu/blogimages/raw/master/img/flowchart.png)

- 插入Flowchart流程图，[参考网址](http://flowchart.js.org/)

- 插入classDiagram类图，[参考网址](https://mermaid-js.github.io/mermaid/#/classDiagram)

![](https://gitee.com/maoshunfu/blogimages/raw/master/img/classDiagram.png)