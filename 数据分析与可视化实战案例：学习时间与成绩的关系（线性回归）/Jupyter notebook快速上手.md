# Jupyter notebook快速上手

> 张子豪 同济大学研究生

的Bilibili视频教程：[同济子豪兄](https://space.bilibili.com/1900783/#/)<br>

知乎专栏：[人工智能小技巧](https://zhuanlan.zhihu.com/c_1032626015746502656)<br>

简书专栏：[人工智能小技巧](https://www.jianshu.com/u/38cccf09b515)<br>

子豪兄的粉丝答疑交流QQ群：953712961

[TOC]

# 为什么学Jupyter notebook？

![jupyter notebook](https://upload-images.jianshu.io/upload_images/13714448-24964dfe5bf967db.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

能够编写、运行python文件的程序很多，比如python安装自带的IDLE、程序员喜爱的pycharm、数据科学全家桶Anaconda，还有Spyder、Thonny等。

而我，独爱jupyter notebook。

Jupyter notebook是用python进行数据科学、机器学习的必备工具。

突出优点：

- 学习Jupyter notebook非常容易，按照我的视频教程一步步做，再自己尝试一下，之后写代码即可健步如飞。

- 能够独立运行一个、几个或全部python代码块，更容易看到中间变量的值，从而进行调试
- 可以插入Markdown说明文字和Latex数学公式，让枯燥的代码充满颜值，可读性爆表
- 能够调用Ipython丰富的“魔法函数”，比如程序计时、重复运行、显示图片等
- 写好的代码和文档能够以网页和ppt的形式在线分享。[在线看Jupyter notebook文件](<https://nbviewer.jupyter.org/>)<br>
- 可以在云端远程服务器运行，不需本地安装配置各种环境。[体验一下](<https://jupyter.org/try>)<br>

比如下图，包含了Markdown说明文档、代码块、代码运行结果、图片嵌入等元素，特别适合Python数据科学和机器学习撰写文档。

![jupyter notebook代码分块运行、嵌入Markdown文档和图片](https://upload-images.jianshu.io/upload_images/13714448-2443a11c336e5dcb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

吴恩达的《深度学习》慕课的课后编程作业、大数据竞赛网站Kaggle上的代码文档、美国大学的数据科学课程的课后资料及编程作业，都是以jupyter notebook文件的形式给出的，也就是`.ipynb`文件。

> 其实Jupyter notebook不止可以运行python，还可以运行julia、R、Javascript等语言，这也是`jupyter`这个名字的由来。[Jupyter notebook支持的编程语言](<https://github.com/jupyter/jupyter/wiki/Jupyter-kernels>)<br>
>
> Jupyter notebook集编程和写作于一身，这就叫做“文学编程”。

# Jupyter notebook——在浏览器网页中运行python

## Ipython内核——更高级的python解释器

Jupyter notebook是基于Ipython内核的，在浏览器中以网页形式运行Python代码的工具，十分方便。

> Ipython是啥？
>
> Ipython可以理解成更高级的python解释器，相比原生的python交互式命令行，Ipython有更强大的命令计数、自动补全等交互功能。
>
> Spyder和Jupyter notebook都是以Ipython为内核的。

![ipython](https://upload-images.jianshu.io/upload_images/13714448-a2490a2882107148.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 安装Jupyter notebook

如果你安装了python数据科学全家桶Anaconda，那么其中自带了Jupyter notebook。

如果你没安装Anaconda，可以直接在命令行里运行这行命令

```shell
pip install jupyter -i https://pypi.tuna.tsinghua.edu.cn/simple
```

## 运行Jupyter notebook

打开命令行，输入`jupter notebook`，回车。稍等片刻即可跳出浏览器网页。

![jupyter notebook打开界面](https://upload-images.jianshu.io/upload_images/13714448-803f32720cf0278e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击右边的New-Python3即可创建python文档。

点击New-Folder可以创建新文件夹。

点击New-Text File可以创建空的`.txt`文件。

点击New-Terminal可以打开操作系统命令行，你可以使用操作系统对应的命令行进行目录切换、解压文件等操作。

勾选文件夹，点击rename即可重命名

![勾选文件夹，点击rename重命名](https://upload-images.jianshu.io/upload_images/13714448-8919418efb809f54.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

最常用的是点击右边的New-Python3，创建python文档。

# 用Jupyter notebook写python代码

## 写下并运行第一行python代码

点击左上角`Untitled`给新建的python文档文件重新命名。

![重命名](https://upload-images.jianshu.io/upload_images/13714448-13476809ac9b10e3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在代码框中输入第一行python代码，shift+回车运行

![输入第一行python代码](https://upload-images.jianshu.io/upload_images/13714448-540050c6c6fd06ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![运行第一行python代码](https://upload-images.jianshu.io/upload_images/13714448-6be52bc326129244.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 蓝绿两模式：命令模式、编辑模式

Jupyter notebook中，代码和文档都存在于一个个单元格中，每个单元格都有蓝色和绿色两种状态。

- 命令模式（蓝色）：用于执行键盘输入的快捷命令（新增单元格、剪切、复制等等）。通过 `Esc` 键从绿色的编辑模式切换到蓝色的命令模式，此时单元左侧显示蓝色竖线。

- 编辑模式（绿色）：编辑文本和代码。选中单元并按 `Enter` 键进入编辑模式，此时单元左侧显示绿色竖线。

> 命令模式和编辑模式，其实是源自于著名的vim编辑器，vim编辑器以特别难学和学成之后可以超神而闻名于世。

## 两种单元格：代码单元格和Markdown单元格

Jupyter notebook中，有两种单元格：代码单元格和Markdown单元格。

- 代码单元格：这里是你编写代码的地方，通过按 `Shift + Enter` 运行代码，其结果显示在本单元下方。代码单元左边有 `In [1]:` 这样的序列标记，方便人们查看代码的执行次序。在蓝色命令模式下，按`y`键可以将Markdown单元格转换为代码单元格。
- Markdown 单元格：在这里对文本进行编辑，采用 markdown 的语法规范，可以设置文本格式、插入链接、图片甚至数学公式。同样使用 `Shift + Enter` 运行 markdown 单元来显示渲染后的文本。在蓝色命令模式下按`m`键可以将代码单元格转换为Markdown单元格。

> Markdown是程序员通用的撰写文档的语法，可以轻松实现标题、引用、链接、图片等，非常简洁易学，Github代码托管网站、有道云笔记、简书、知乎、CSDN论坛、电子邮件等都支持Markdown语法。
>
> 学习Markdown，推荐我制作的博客和视频教程：
>
> [二十分钟精通排版神器Markdown，从此word和秀米是路人](<https://www.jianshu.com/p/4475b9d8810f>)<br>
>
> [Bilibili视频：二十分钟精通排版神器Markdown](<https://www.bilibili.com/video/av35579542>)<br>

编辑Markdown单元格，输入以下内容：

```markdown
# 我是Markdown一号标题
## 我是Markdown二号标题
### 我是Markdown三号标题
>我是引用，我这行开头有一个灰色竖杠

[我是外部链接，点我上百度](www.baidu.com)
![我是图片](https://i1.hdslb.com/bfs/face/c59e147cd3b1f6a7bb88690933499354a024b280.jpg@68w_68h.webp)
```

![编辑Markdown单元格](https://upload-images.jianshu.io/upload_images/13714448-7bf02cfeab7ecf42.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

然后按`shift`+`Enter`运行该单元格。

![Markdown渲染效果](https://upload-images.jianshu.io/upload_images/13714448-6ff0bf8ba88c6b6c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 抛弃鼠标，只用键盘

下面介绍Jupyter notebook快捷键，掌握这些快捷键之后，你将彻底解放你拿鼠标的那只手，更专注、高效地敲代码了。

## 最常用快捷键（必会）

h 查看所有快捷键

Enter 从命令模式进入编辑模式

Esc 从编辑模式退回到命令模式

m 将代码单元格转换为Markdown单元格

y 将Markdown单元格转换为代码单元格

shift+Enter 运行本单元格，选择下面的代码块

ctrl+Enter 运行本单元格

alt+Enter 运行本单元格，在下方新建一个单元格

a 在上方新建一个单元格（above）

b 在下方新建一个单元格（below）

d 删除选中的单元格（delete）

x 剪切本单元格

c 复制本单元格

shift v 粘贴到上面

v 粘贴到下面

l 显示代码行号



## 所有快捷键

h 查看所有快捷键

![命令模式快捷键](https://upload-images.jianshu.io/upload_images/13714448-b9df2500cb80d59c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![编辑模式快捷键](https://upload-images.jianshu.io/upload_images/13714448-62d750fe7af8823e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 在Markdown单元格中输入数学公式

分别在两个Markdown单元格内输入以下内容：

```latex
这是爱因斯坦的质能转换方程$E=mc^2$，揭示了质量和能量之间的关系
```

```latex
这是一元二次方程求解公式
$$x = \frac{-b\pm \sqrt{b^2-4ac}}{2a}$$
初中数学内容
```

![在Markdown单元格中输入Latex公式](https://upload-images.jianshu.io/upload_images/13714448-0bbb7722aef50550.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

按`shift`+`Enter`渲染运行：

![渲染之后的Latex数学公式](https://upload-images.jianshu.io/upload_images/13714448-7fa655030c9da5ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 数据分析与可视化实战案例：学习时间与成绩的关系（线性回归）

先用excel把玩数据

![excel中的线性回归](https://upload-images.jianshu.io/upload_images/13714448-8aeb063599a395b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

观察数据、导入数据、划分特征和标签、划分训练集和测试集、构建模型，模型可视化

# 用Jupyter notebook制作ppt并在线分享



# 参考博客

[左手代码，右手写作：你必须会的Jupyter Notebook](<https://www.jianshu.com/p/86117613b7a6>)<br>

[二十分钟精通排版神器Markdown，从此word和秀米是路人](<https://www.jianshu.com/p/4475b9d8810f>)<br>

[Bilibili视频：二十分钟精通排版神器Markdown](<https://www.bilibili.com/video/av35579542>)<br>

