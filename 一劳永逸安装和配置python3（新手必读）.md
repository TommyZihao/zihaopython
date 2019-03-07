一劳永逸安装和配置python3.7.2（新手必读）
=====================================

> 作者：张子豪（同济大学开源软件协会）
>
> 知乎、简书、微信公众号：[人工智能小技巧](https://zhuanlan.zhihu.com/c_1032626015746502656)
>
> [跟子豪兄趣学python系列课程](https://github.com/TommyZihao/zihaopython)

本文旨在手把手带领python初学者一劳永逸解决所有环境搭建、安装配置问题，并介绍几种常见的python开发工具。重点介绍python3.7.2的安装、用IDLE的交互式界面和脚本编辑界面运行python代码、用命令行界面运行python代码、pip包管理器切换国内镜像、安装第三方模块。

[本文配套Bilibili视频：一劳永逸安装和配置python3.7.2（新手必读）](https://www.bilibili.com/video/av45546100)

【目录】

-   [前言](#前言)
-   [1、安装python3.7.2](#安装python3.7.2)
    -   [下载方式一：百度网盘链接（推荐）](#下载方式一百度网盘链接推荐)
    -   [下载方式二：python官网下载](#下载方式二python官网下载)
    -   [安装](#安装)
-   [2、通过python自带的IDLE编写和运行python程序](#通过python自带的idle编写和运行python程序)
    -   [打开IDLE](#打开idle)
    -   [逐行输入并运行python代码：交互式界面](#逐行输入并运行python代码交互式界面)
    -   [IDLE快捷键](#idle快捷键)
    -   [一次性执行多行代码：脚本文件界面](#一次性执行多行代码脚本文件界面)
-   [3、通过windows命令行编写和运行python程序](#通过windows命令行编写和运行python程序)
    -   [进入windows命令行](#进入windows命令行)
    -   [逐行输入并运行python代码：交互式界面](#逐行输入并运行python代码交互式界面-1)
    -   [命令行快捷键](#命令行快捷键)
    -   [在windows命令行中运行.py格式的python脚本文件](#在windows命令行中运行.py格式的python脚本文件)
-   [4、使用pip工具安装python第三方模块：尽享开源社区和计算生态](#使用pip工具安装python第三方模块尽享开源社区和计算生态)
    -   [python的开源社区与计算生态](#python的开源社区与计算生态)
    -   [pip工具：用于下载第三方模块的包管理器](#pip工具用于下载第三方模块的包管理器)
    -   [pip
        install命令下载第三方模块`numpy`](#pip-install命令下载第三方模块numpy)
-   [5、给pip工具更换国内镜像源：让下载速度快到飞起](#给pip工具更换国内镜像源让下载速度快到飞起)
    -   [方法一：一劳永逸配置pip源（推荐）](#方法一一劳永逸配置pip源推荐)
    -   [方法二：临时使用-i参数从国内镜像下载第三方模块](#方法二临时使用-i参数从国内镜像下载第三方模块)
    -   [国内几个知名的python开源镜像站](#国内几个知名的python开源镜像站)
    -   [用pip安装测试几个第三方模块](#用pip安装测试几个第三方模块)
        -   [数据可视化第三方模块`matplotlib`](#数据可视化第三方模块matplotlib)
        -   [中文分词第三方模块`jieba`](#中文分词第三方模块jieba)
        -   [情感分析与文本处理第三方模块`snownlp`](#情感分析与文本处理第三方模块snownlp)
-   [6、常见python开发工具概览](#常见python开发工具概览)
    -   [IDLE：安装自带，简洁易用，新手推荐](#idle安装自带简洁易用新手推荐)
    -   [thonny：一步步运行调试，查看变量值变化，新手推荐](#thonny一步步运行调试查看变量值变化新手推荐)
    -   [Anaconda：科学计算全家桶](#anaconda科学计算全家桶)
    -   [Spyder：和Matlab超像的python编辑工具](#spyder和matlab超像的python编辑工具)
    -   [Jupyter
        notebook：分块运行代码单元，数据分析必备](#jupyter-notebook分块运行代码单元数据分析必备)
    -   [PyCharm：专业程序员，大型项目适用](#pycharm专业程序员大型项目适用)

# 前言

回忆我当初python零基础入门的时候，最讨厌做的事情就是手忙脚乱地搭建各种开发环境、配置各种环境变量、国内镜像、开发工具和IDE，切换各种python版本和解释器。虽然现在看来这些东西都很简单（就是本文所讲内容），但是对新手来说，遇到任何一个小bug都会让他浪费大量时间精力去解决，甚至直接劝退弃学。我之前见到一个同学，卡在第一步安装python，学了半年，连交互式界面和脚本编辑界面都搞不清楚。于是我就想做一个教程，一站式解决python的所有安装配置和开发工具问题，之后就可以专注于享受代码本身和解决问题，享受python庞大的开源社区和计算生态。

本文是很多程序员多年的经验炼出的真金，只需按照步骤一步步来就行。学过了本课的内容，你就可以昂首挺胸迎接后续内容。之后的python课程都可以通过windows命令行和python自带的IDLE完成，你可以专注享受编程本身，而不用去为安装搭建配置各种环境而苦恼了。

大家可以在知乎专栏”人工智能小技巧“上看到这篇博客，也可以在开源社区[github:跟子豪兄趣学python系列课程](https://github.com/TommyZihao/zihaopython)    上看到我们整个python系列课程的所有视频链接、博客文档和源代码。

请大家在座位上坐好 系好安全带 收起小桌板 手机调至静音模式 我们马上起飞。

[本文配套Bilibili视频：一劳永逸安装和配置python3.7.2（新手必读）](https://www.bilibili.com/video/av45546100)

# 1、安装python3.7.2

## 下载方式一：百度网盘链接（推荐）

链接：https://pan.baidu.com/s/1NBLve375kK6bEvkcdtGEFA   

提取码：znrp   

选择自己电脑对应的操作系统下载即可。

## 下载方式二：python官网下载

> 最好用迅雷下载，否则速度会很慢

[python-3.7.2-windows-64位（点我下载）](https://www.python.org/ftp/python/3.7.2/python-3.7.2-amd64.exe)  

[python-3.7.2-windows-32位（点我下载）](https://www.python.org/ftp/python/3.7.2/python-3.7.2.exe)  

[python-3.7.2-macOS-64位/32位（点我下载）](https://www.python.org/ftp/python/3.7.2/python-3.7.2-macosx10.6.pkg)  

## 安装

一定要勾选最后一项 **Add python3.7 to PATH**，然后点`Install Now`。

![一定要勾选最后一项 Add python3.7 to PATH](https://upload-images.jianshu.io/upload_images/13714448-e47d64f4db451efc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

安装成功

![安装成功](https://upload-images.jianshu.io/upload_images/13714448-a0145cd53f3e179c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2、通过python自带的IDLE编写和运行python程序

## 打开IDLE

开始菜单里搜`python`或者`IDLE`，即可看到IDLE，IDLE是python安装自带的集成开发工具，对于新手来说绝对够用，我们后续的课程也全都可以用IDLE实现。

IDLE最大的优点就是：安装自带、打开方便、像坟墓一样简洁。

> Python的创始人“龟叔”Guido van Rossum也参与了IDLE的开发。

![找到IDLE](https://upload-images.jianshu.io/upload_images/13714448-bee6c6bfbe224324.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

打开IDLE之后，在上方的`Options`-->`Configure IDLE`中可修改字号、字体、颜色等配置。

![进入配置界面](https://upload-images.jianshu.io/upload_images/13714448-58dcc1a0db858fe3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

调大字号

![调大字号](https://upload-images.jianshu.io/upload_images/13714448-63bd1c3f0e9c42f1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 逐行输入并运行python代码：交互式界面

三个大于号`>>>`表示目前处于交互式命令行界面，用户可以逐行输入并逐行运行python代码。

![IDLE交互式命令行界面](https://upload-images.jianshu.io/upload_images/13714448-bb3b6e87d261b599.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

源代码：

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
>>> print(a,b,a+b,a-b)
5 6 11 -1
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

`ctrl+n`新建脚本文件，进入脚本文件编辑界面。

与逐行输入逐行运行代码的交互式命令行不同，在脚本文件界面中，我们可以事先写好多行代码然后一次性统一执行。
![脚本文件界面](https://upload-images.jianshu.io/upload_images/13714448-dc508b5026355f22.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

源代码（可直接复制粘贴到脚本文件里面）：

```python
for i in range(100):
    if i % 2 == 0:
        print(i,'是偶数')
    else:
        print(i,'是奇数')
print('100以内的数判别完毕')
```

点击`Run`-->`Run Module`执行脚本文件的代码，也可以直接按`F5`键运行。在运行之前会提示先保存文件。

![执行脚本文件的代码](https://upload-images.jianshu.io/upload_images/13714448-66f3f8958630c4b0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



运行结果

![脚本运行结果](https://upload-images.jianshu.io/upload_images/13714448-69494e209cd5afc4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 3、通过windows命令行编写和运行python程序

## 进入windows命令行

- 方法一：直接桌面左下角搜索栏里搜索`cmd`或`terminal`或`命令提示符`。

![进入windows命令行](https://upload-images.jianshu.io/upload_images/13714448-a3a668e34db01d46.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 方法二：同时按键盘上的`windows键+r键`，在跳出的运行对话框里输入cmd，回车

  ![在"运行"对话框中输入cmd，进入windows命令行](https://upload-images.jianshu.io/upload_images/13714448-e3cdc790a7b22d3f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 逐行输入并运行python代码：交互式界面

这个黑乎乎的界面叫做windows命令行，也叫做DOS界面。输入`python`，然后回车，即可进入python的交互式界面。

![windows命令行中逐行输入并运行python代码](https://upload-images.jianshu.io/upload_images/13714448-6b7910c48b6003c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

代码如下：

> 在python的语法中不能出现中文的引号、括号、逗号、句号

```python
Microsoft Windows [版本 10.0.17134.590]
(c) 2018 Microsoft Corporation。保留所有权利。

C:\Users\张子豪>python
Python 3.7.2 (tags/v3.7.2:9a3ffc0492, Dec 23 2018, 23:09:28) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 2**4
16
>>> 3+5-2
6
>>> 5*7
35
>>> 987/654
1.5091743119266054
>>> 23%10
3
>>> a = 654%10
>>> a
4
>>> b = 8//3
>>> b
2
>>> print(a)
4
>>> print(a,b,a+b,a-b)
4 2 6 2
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

在windows命令行中，使用`cd+路径`的命令切换到.py文件所在的目录

比如，我刚刚用IDLE写的判定100以内奇偶数的程序，放在`C:\Users\张子豪\AppData\Local\Programs\Python\Python37`目录下，我就需要在windows命令行界面中用`cd`命令切换到这个目录

再用`python+空格+文件名`的方式运行.py脚本文件

![cmdtest.gif](https://upload-images.jianshu.io/upload_images/13714448-1a5b8fa706ca99d8.gif?imageMogr2/auto-orient/strip)

![在windows命令行中执行python脚本文件](https://upload-images.jianshu.io/upload_images/13714448-1c0876d9fdb420f5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 4、使用pip工具安装python第三方模块：尽享开源社区和计算生态

## python的开源社区与计算生态

python为什么这么火？

1、简洁易学，语法很类似人类的自然语言

2、庞大的开源生态和计算社区。让全世界最优秀程序员写的代码为我们所用，站在巨人的肩膀上开发，不需要重复造轮子。

[Python计算生态：pypi社区](https://pypi.org/)  

一些知名的python第三方模块，我们这个python系列课程有大量的篇幅介绍这些第三方库的使用。

| 领域                               | python第三方模块                                  |
| ---------------------------------- | ------------------------------------------------- |
| 人工智能与机器学习                 | Tensorflow、Pytorch、Sklearn、MXNet、aip          |
| 数据分析与科学计算                 | Numpy、Pandas、SciPy                              |
| 大数据可视化                       | wordcloud、Matplotlib、Seaborn、Mayavi、pyecharts |
| 图像处理与机器视觉                 | PIL、opencv                                       |
| 自然语言处理、文本处理             | jieba、NLTK、snownlp、PyPDF2、python-docx         |
| 网络爬虫与信息提取                 | Requests、Scrapy、Beautiful Soup、pyquery         |
| 云端Web开发                        | Flask、Django、Pyramid                            |
| 游戏、虚拟现实、艺术设计、人机交互 | pygame、VR Zero、Vizard、Quads、ascii_art、MyQR   |
| 微信、新浪微博开发接口             | WeRobot、weibopy、itchat                          |
| 物联网与智能硬件                   | 树莓派、3D打印机、Arduino单片机、激光雕刻机等模块 |

## pip工具：用于下载第三方模块的包管理器

如何安装开源生态和计算社区的第三方库呢？python安装的时候附带了pip工具

在windows命令行中输入`pip list`或者`pip install`，验证pip是否安装成功。

> 注意，是在windows命令行中输入，而不是在python的交互式命令行中输入。pip工具在使用的时候要联网。

显示pip安装成功的界面：

![显示pip安装成功的界面](https://upload-images.jianshu.io/upload_images/13714448-5b53c83f75c36596.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> `pip list`命令：显示目前pip已经安装好的第三方模块。

## pip install命令下载第三方模块`numpy`

用`pip install+模块名字`命令安装第三方模块，用`pip uninstall+模块名字`命令卸载第三方模块。

```powershell
pip install numpy
```

![直接用pip install numpy命令安装numpy](https://upload-images.jianshu.io/upload_images/13714448-934945bed2af6634.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

你会发现下载的速度很慢，这是因为我们是从国外的开源社区网站下载资源，关山难越，通信阻隔。

为了解决这个问题，我们可以从国内已经下载好的人手里下载，比如，从清华大学开源软件镜像站下载。



# 5、给pip工具更换国内镜像源：让下载速度快到飞起

## 方法一：一劳永逸配置pip源（推荐）

只需在windows命令行中输入一行命令，即可永久设置pip下载源为国内源

```python
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

> 注意：是 `https` 而不是 `http`，`simple` 不能少  



## 方法二：临时使用-i参数从国内镜像下载第三方模块

临时使用`-i`参数从清华大学开源镜像站下载numpy

```powershell
pip install numpy -i https://pypi.tuna.tsinghua.edu.cn/simple
```

> 注意：是 `https` 而不是 `http`，`simple` 不能少  

![通过-i参数从清华大学开源软件镜像站下载第三方库](https://upload-images.jianshu.io/upload_images/13714448-8210ef5dbbb7fc5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

只需在之前的`pip install`后面加上`-i`参数即可指定不同的国内镜像源，下载速度一下子就飞起了。
以下是一些国内知名的开源镜像站，它们的工作就是每隔几分钟就把国外的pypi社区网站上的更新内容下载下来存在国内的服务器上，就像照镜子一样百分百复制，便于国内的用户高速下载。

## 国内几个知名的python开源镜像站

| 国内python开源镜像站 | 网址                                      |
| -------------------- | ----------------------------------------- |
| 清华大学             | https://pypi.tuna.tsinghua.edu.cn/simple/ |
| 中国科学技术大学     | http://pypi.mirrors.ustc.edu.cn/simple/   |
| 豆瓣                 | http://pypi.douban.com/simple/            |
| 阿里云               | http://mirrors.aliyun.com/pypi/simple/    |

安装成功numpy之后，可以在windows命令行或者IDLE中验证

![在IDLE和windows命令行中验证numpy安装成功](https://upload-images.jianshu.io/upload_images/13714448-0a5d5a32fbfd0f90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

再安装pandas库

```python
pip install pandas -i https://pypi.tuna.tsinghua.edu.cn/simple
```





## 用pip安装测试几个第三方模块

### 数据可视化第三方模块`matplotlib`

在windows命令行中输入

```python
pip install matplotlib
```

使用matplotlib可以绘制出各种高大上的数据可视化效果，[点我看一些高大上的案例](https://matplotlib.org/gallery/index.html)   

绘制直线、抛物线函数图像

```python
import numpy as np
import matplotlib.pyplot as plt
x = np.arange(0,10,0.01)
y1 = 2 * x
y2 = 5 * x 
y3 = x ** 2
plt.plot(x,y1,'r',x,y2,'g',x,y3,'b')
plt.show()
```

绘制三角函数图像

```python
import numpy as np
import matplotlib.pyplot as plt
x = np.arange(0,5,0.01)
y1 = np.sin(x)
y2 = np.cos(x)
plt.plot(x,y1,'r',x,y2,'g')
plt.show()
```

![用matplotlib绘制函数图像](https://upload-images.jianshu.io/upload_images/13714448-4b2fc745f9e5f03d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 中文分词第三方模块`jieba`

在windows命令行中输入

```python
pip install jieba
```

直接调用`jieba`模块进行中文分词

```python
import jieba
a = jieba.lcut('中国是个伟大的国家')
print(a)
```

![使用jieba进行中文分词](https://upload-images.jianshu.io/upload_images/13714448-84e330335d62cf86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 情感分析与文本处理第三方模块`snownlp`

在windows命令行中输入

```python
pip install snownlp
```

直接调用`snownlp`模块进行文本分析

```python
import snownlp
s = snownlp.SnowNLP('这个东西真心很赞')
print('中文分词',s.words)
print('情感分析',s.sentiments)
print('转成拼音',s.pinyin)
print('词频',s.tf)
print('提取三个关键词',s.keywords(3))
```



# 6、常见python开发工具概览

进入windows命令行，一个命令安装几个常用的Python集成开发环境（IDE）

```python
pip install thonny jupyter spyder
```

## IDLE：安装自带，简洁易用，新手推荐

![IDLE：交互式界面与脚本编辑界面](https://upload-images.jianshu.io/upload_images/13714448-e37a0661d61ba70e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## thonny：一步步运行调试，查看变量值变化，新手推荐

![thonnytest1.gif](https://upload-images.jianshu.io/upload_images/13714448-fb6ef1bf4e622b2b.gif?imageMogr2/auto-orient/strip)

## Anaconda：科学计算全家桶

> 个人建议：新手不需要用Anaconda，需要什么库直接按照上述方法`pip install`即可，再学一下`pipenv`虚拟环境搭建，就可以了。

Anaconda包括Conda包管理器、Python解释器以及一大堆安装好的科学计算工具包，比如：numpy、pandas等。因为包含了大量的科学计算包，Anaconda 的下载文件比较大（约 600 MB），如果只需要某些包，或者需要存储空间，可以使用占用空间较小的Miniconda（仅包含包管理器conda和 Python解释器）。

Anaconda可以从清华大学开源软件镜像站下载，最新版本下载链接如下：

[Anaconda3-5.3.1-windows64位](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-Windows-x86_64.exe)  

[Anaconda3-5.3.1-windows32位](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-Windows-x86.exe)  

[Anaconda3-5.3.1-MacOSX-x86_64.sh](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-MacOSX-x86_64.sh)  

[Anaconda3-5.3.1-MacOSX-x86_64.pkg](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-MacOSX-x86_64.pkg)  

![Anaconda内置的一部分第三方库](https://upload-images.jianshu.io/upload_images/13714448-b319b5ac6565710b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Miniconda 是一个 Anaconda 的轻量级替代，默认只包含了 python 和 conda，但是可以通过 pip 和 conda 来安装所需要的包。

[Miniconda3-latest-Windows-64位](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Windows-x86_64.exe)   

[Miniconda3-latest-Windows-32位](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Windows-x86.exe)   

[Miniconda3-latest-MacOSX-x86_64.sh](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-MacOSX-x86_64.sh)   

[Miniconda3-latest-MacOSX-x86_64.pkg](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-MacOSX-x86_64.pkg)   

## Spyder：和Matlab超像的python编辑工具



## Jupyter notebook：分块运行代码单元，数据分析必备



## PyCharm：专业程序员，大型项目适用

pycharm分为免费的社区版和付费的专业版，对于初学者而言，免费的社区版绝对够用。

pycharm的界面冷若冰霜，代码纷繁复杂，窗口星罗棋布，环境浩如烟海，文档汗牛充栋，还都是英文，适合开发大型项目的专业程序员使用。

但是，pycharm提供了语法纠错、代码高亮、文件树浏览、断点调试等诸多专业功能。

![pycharm界面](https://upload-images.jianshu.io/upload_images/13714448-d08f1c4b83b8c22f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>配置环境过程中还有一些奇技淫巧，比如切换不同python版本的解释器，用pipenv或conda配置虚拟环境等，我们会在后续课程中需要用到的时候讲解
