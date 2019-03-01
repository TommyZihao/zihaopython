# 一劳永逸安装和配置python3（新手必读）

>作者：张子豪（同济大学开源软件协会）    
>
>知乎专栏：[人工智能小技巧](https://zhuanlan.zhihu.com/c_1032626015746502656)      
>
>微信公众号：**人工智能小技巧**  

[本文配套B站视频：一劳永逸安装和配置python3（新手必读）](https://space.bilibili.com/1900783/#/)   

本文旨在手把手带领python初学者一劳永逸解决所有环境搭建、安装配置问题。

- 1、安装python3（3.7.2最新版本）      

- 2、通过windows命令行编写和运行python程序     

- 3、通过python自带的IDLE编写和运行python程序  

- 4、使用pip工具安装python第三方模块：尽享开源社区和计算生态 

- 5、一劳永逸给pip工具更换国内镜像源：让下载达到火箭速度

- 6、其它常见python开发工具概览  

  - Anaconda：常用第三方模块全家桶，安装它等于安装了全宇宙

  - thonny：可以逐行运行调试的python工具，新手推荐
  - spyder：和matlab超像的python编辑工具
  - jupyter notebook：可以逐个运行代码区块，数据分析必备
  - pycharm：专业程序员，大型项目适用

# 前言

前几天我跟一个程序员聊天，

回忆我当初python零基础入门的时候，我最讨厌做的事情就是搭建各种开发环境、配置各种开发工具和IDE，切换各种python版本和解释器。虽然现在看来这些东西都很简单（就是本文所讲内容），但是对新手来说，遇到任何一个小bug都会让他浪费大量时间精力去解决，甚至直接劝退弃学。于是我想

多年的经验炼出的真金，只需按照这个步骤一步步来就行

大家可以在知乎上看到这篇博客



# 1、安装python3（3.7.2最新版本）

加path

验证安装成功



# 2、通过windows命令行编写和运行python程序

交互式界面：三个大于号

加减乘除乘方整除取余

赋值、变量运算

print字符串、变量

快捷键

方向键上下

ctrl c

ctrl z回车退出命令行

exit（）

quit（）

> 在python的语法中不能出现中文的引号、括号、逗号、句号

# 3、通过python自带的IDLE编写和运行python程序

开始菜单里搜python，即可看到IDLE

IDLE是python安装的时候自带的集成开发工具，对于新手来说绝对够用，我们后续的课程也都可以用IDLE实现

最大的优点就是：像坟墓一样简洁

交互式界面



快捷键 alt p n

p-previous

n-new



脚本文件界面 ctrl n





# 4、使用pip工具安装python第三方模块：尽享开源社区和计算生态

python为什么这么火，一个是特别简单易学，语法很类似人类的自然语言，简洁，不需要花括号和括号之类的处理条件判断和循环，只需要控制缩进就可以了

还有一个原因就是庞大的开源生态和计算社区，让我们能够站在巨人的肩膀上编程，让全世界的程序员给我们写代码，不需要重复造轮子

pypi社区

一些知名的python第三方模块

| 领域               | 第三方模块的名字             |
| ------------------ | ---------------------------- |
| 人工智能与机器学习 | tensorflow、pytorch、sklearn |
| 数据分析与科学计算 |                              |
| 数据可视化         | wordcloud、matplotlib、      |
| 爬虫与网络信息提取 |                              |
| 智能硬件           |                              |



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





# 5、一劳永逸给pip工具更换国内镜像源：让下载达到火箭速度



# 6、常见python开发工具概览



 
