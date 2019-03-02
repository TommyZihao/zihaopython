# 一劳永逸安装和配置python3（新手必读）

>作者：张子豪（同济大学开源软件协会）    
>
>知乎、简书微信公众号：[人工智能小技巧](https://zhuanlan.zhihu.com/c_1032626015746502656)      
>

本文旨在手把手带领python初学者一劳永逸解决所有环境搭建、安装配置问题，并介绍几种常见的python开发工具。

 [本文配套B站视频：一劳永逸安装和配置python3（新手必读）](https://space.bilibili.com/1900783/#/)   

[TOC]

# 前言

前几天我跟一个程序员聊天，

回忆我当初python零基础入门的时候，我最讨厌做的事情就是搭建各种开发环境、配置各种开发工具和IDE，切换各种python版本和解释器。虽然现在看来这些东西都很简单（就是本文所讲内容），但是对新手来说，遇到任何一个小bug都会让他浪费大量时间精力去解决，甚至直接劝退弃学。于是我想

多年的经验炼出的真金，只需按照这个步骤一步步来就行

大家可以在知乎上看到这篇博客

本文旨在手把手带领python初学者一劳永逸解决所有环境搭建、安装配置问题，并介绍几种常见的python开发工具。



# 1、安装python3（3.7.2最新版本）

## 下载

Python官方网站：www.python.org

进入后点击Download

[python-3.7.2-windows-64位](https://www.python.org/ftp/python/3.7.2/python-3.7.2-amd64.exe)  

[python-3.7.2-windows-32位](https://www.python.org/ftp/python/3.7.2/python-3.7.2.exe)  

[python-3.7.2-macOS-64位/32位](https://www.python.org/ftp/python/3.7.2/python-3.7.2-macosx10.6.pkg)  

## 安装

加path

验证安装成功

# 2、通过python自带的IDLE编写和运行python程序

## 打开IDLE

开始菜单里搜python，即可看到IDLE，IDLE是python安装自带的集成开发工具，对于新手来说绝对够用，我们后续的课程也全都可以用IDLE实现。

IDLE最大的优点就是：安装自带、打开方便、像坟墓一样简洁。

> Python的创始人“龟叔”Guido van Rossum也参与了IDLE的开发。

![打开IDLE](https://upload-images.jianshu.io/upload_images/13714448-a585531fe8207183.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

打开IDLE之后，在上方的`Options`-->`Configure IDLE`中可修改字号、字体、颜色等配置。

## 逐行输入并运行python代码：交互式界面

交互式界面，三个大于号

```python
>>> 4+7
11
>>> 123-45
78
>>> 56*9
504
>>> 987/543
1.8176795580110496
>>> 2**5
32
>>> 123//10
12
>>> 123%10
3
>>> a = 5
>>> b = 6
>>> a
5
>>> b
6
>>> a+b
11
>>> print(a)
5
>>> print('hello world!')
hello world!
```

## IDLE快捷键

| 快捷键   | 功能                                 |
| -------- | ------------------------------------ |
| `alt+p`  | 回到上一条运行过的命令（p-previous） |
| `alt+n`  | 回到下一条运行过的命令（n-new）      |
| `tab`    | 自动补齐代码                         |
| `ctrl+c` | 强制结束当前正在运行的python命令     |
| `ctrl+o` | 打开文件                             |
| `ctrl+n` | 新建脚本文件，进入文件编辑界面       |



## 一次性执行多行代码：脚本文件界面

`ctrl+n`新建脚本文件，进入文件编辑界面。

与逐行输入逐行运行代码的交互式命令行不同，在脚本文件界面中，我们可以事先写好多行代码然后一次性统一执行。







# 3、通过windows命令行编写和运行python程序

## 进入windows命令行

- 方法一：直接桌面左下角搜索栏里搜索`cmd`或`terminal`或`命令提示符`。

![进入windows命令行](https://upload-images.jianshu.io/upload_images/13714448-a3a668e34db01d46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 方法二：同时按键盘上的`windows键+r键`，在跳出的运行对话框里输入cmd，回车

  ![在"运行"对话框中输入cmd，进入windows命令行](https://upload-images.jianshu.io/upload_images/13714448-e3cdc790a7b22d3f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 逐行输入并运行python代码：交互式界面

![windows命令行中逐行输入并运行python代码](https://upload-images.jianshu.io/upload_images/13714448-6b7910c48b6003c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

代码如下：

> 在python的语法中不能出现中文的引号、括号、逗号、句号

```python
Microsoft Windows [版本 10.0.17134.590]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\张子豪>python
Python 3.6.5 |Anaconda, Inc.| (default, Mar 29 2018, 13:32:41) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 2**4
16
>>> 3+5-2
6
>>> 5*7
35
>>> 987/654
1.5091743119266054
>>> a = 23%10
>>> a
3
>>> b = 8//3
>>> b
2
>>> print(a,b)
3 2
>>> print(a)
3
>>> print(a,b,a+b,a-b)
3 2 5 1
>>> print('hello world!')
hello world!
>>> exit()

C:\Users\张子豪>
```

## 命令行快捷键

| 快捷键                 | 功能                             |
| ---------------------- | -------------------------------- |
| `方向键上下键`         | 切换到之前运行过的命令           |
| `ctrl+c`               | 强制结束当前正在运行的python命令 |
| `ctrl+z`，再按回车     | 退出python，回到windows命令行    |
| 输入`exit()`，再按回车 | 退出python，回到windows命令行    |
| 输入`quit()`，再按回车 | 退出python，回到windows命令行    |

## 在windows命令行中运行.py格式的python脚本文件



# 4、使用pip工具安装python第三方模块：尽享开源社区和计算生态

python为什么这么火，一个是特别简单易学，语法很类似人类的自然语言，简洁，不需要花括号和括号之类的处理条件判断和循环，只需要控制缩进就可以了

还有一个原因就是庞大的开源生态和计算社区，让我们能够站在巨人的肩膀上编程，让全世界的程序员给我们写代码，不需要重复造轮子

[Python计算生态：pypi社区](https://pypi.org/)  

一些知名的python第三方模块

| 领域                         | python第三方模块                                  |
| ---------------------------- | ------------------------------------------------- |
| 人工智能与机器学习           | Tensorflow、Pytorch、Sklearn、MXNet、aip          |
| 数据分析与科学计算           | Numpy、Pandas、SciPy                              |
| 数据可视化                   | wordcloud、Matplotlib、Seaborn、Mayavi、pyecharts |
| 图像处理                     | PIL、opencv                                       |
| 文本处理                     | jieba、NLTK、snownlp、PyPDF2、python-docx         |
| 网络爬虫与信息提取           | Requests、Scrapy、Beautiful Soup、pyquery         |
| 云端Web开发                  | Flask、Django、Pyramid                            |
| 游戏、虚拟现实、艺术设计     | pygame、VR Zero、Vizard、Quads、ascii_art、MyQR   |
| 微信、新浪微博、微软开发接口 | WeRobot、weibopy                                  |



如何安装开源生态和计算社区的第三方库呢？python安装的时候附带了pip工具

命令行验证

pip、pip list



numpy

加-i参数 国内镜像的原理 喝椰子

验证 import

再安装pandas库



一劳永逸配置pip源

制作pip.ini文件

c盘 用户 allusers 



snownlp

```python
import snownlp
s = snownlp.SnowNLP('这个东西真心很赞')
print('中文分词',s.words)
print('情感分析',s.sentiments)
print('转成拼音',s.pinyin)
print('词频',s.tf)
print('提取三个关键词',s.keywords(3))
```





# 5、给pip工具更换国内镜像源：让下载达到火箭速度



# 6、常见python开发工具概览

## IDLE：安装自带的开发环境，像坟墓一样简洁



## thonny：可以逐行运行调试的python工具，新手推荐



## Anaconda：常用第三方模块全家桶，安装它等于安装了全宇宙



## Spyder：和Matlab超像的python编辑工具



## Jupyter notebook：分块运行代码单元，数据分析必备



## PyCharm：专业程序员，大型项目适用

 













