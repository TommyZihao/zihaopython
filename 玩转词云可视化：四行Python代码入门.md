# 玩转词云可视化：四行Python代码入门

[TOC]

# 本文概要

从四行代码开始，一步步教你做出高大上的词云图片，可视化生动直观展示出枯燥文字背后的核心概念。进一步实现修改字体、字号、背景颜色、词云形状、勾勒边框、颜色渐变等高级玩法。

学完本课之后，你可以将四大名著、古典诗词、时事新闻、法律法规、政府报告、小说诗歌等大段文本做成高大上的可视化词云，还可以将你的微信好友个性签名导出，看看你微信好友的“画风”是怎样的。

![三国演艺词云](https://upload-images.jianshu.io/upload_images/13714448-e6a1c4c8bfbf0471.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

作者：同济大学 子豪兄  2019-5-23

Bilibili视频教程：[同济子豪兄-子豪兄opencv-python教程](https://space.bilibili.com/1900783/#/)<br>知乎专栏：[人工智能小技巧](https://zhuanlan.zhihu.com/c_1032626015746502656)<br>简书专栏：[人工智能小技巧](https://www.jianshu.com/u/38cccf09b515)<br>Github：[TommyZihao](<https://github.com/TommyZihao>)<br>

# `粉丝答疑交流QQ群：953712961`

![子豪兄的赞赏码](https://upload-images.jianshu.io/upload_images/13714448-bec288cb077c7f08.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 先体验一把——词云图片制作微信小程序

![词云制作微信小程序](https://upload-images.jianshu.io/upload_images/13714448-d2f670f92db778fb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 安装本课程所需的所有第三方模块

## 一行命令安装（推荐，适用于99.999%的情况）

打开命令行，输入下面这行命令，回车执行即可。

```powershell
pip install numpy matplotlib pillow wordcloud imageio jieba snownlp itchat -i https://pypi.tuna.tsinghua.edu.cn/simple
```

## 如果安装过程中报错（0.001%会发生）

> 如果报错：`Microsoft Visual C++ 14.0 is required.`
>
> 解决方法：
>
> 到 http://www.lfd.uci.edu/~gohlke/pythonlibs/#wordcloud 页面下载所需的wordcloud模块的.whl文件，再用pip安装下载的文件。
>
> 比如，对于64位windows操作系统，python版本为3.6的电脑，就应该下载
>
> `wordcloud-1.4.1-cp36-cp36m-win_amd64.whl`这个文件
>
> 下载后打开命令行，使用cd命令切换到该文件的路径，执行`pip install wordcloud-1.4.1-cp36-cp36m-win_amd64.whl`命令，即可安装成功。



# 四行Python代码上手词云制作

## 1号词云：葛底斯堡演说黑色背景词云（4行代码上手）

```python
import wordcloud

w = wordcloud.WordCloud()

w.generate('and that government of the people, by the people, for the people, shall not perish from the earth.')

w.to_file('output.png')
```

运行完成之后，到这个python脚本文件所在的文件夹下，打开`output.png`图片文件。可以看出，wordcloud自动将`and that by the not from`等废话词组过滤掉，并且把出现次数最多的`people`大号显示。

![1号词云：葛底斯堡演说黑色背景词云](https://upload-images.jianshu.io/upload_images/13714448-468d2f893ab20dbb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 子豪兄带你逐行读代码

```python
# 1号词云：葛底斯堡演说黑色背景词云
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作第三方库wordcloud
import wordcloud

# 创建词云对象，赋值给w，现在w就表示了一个词云对象
w = wordcloud.WordCloud()

# 调用词云对象的generate方法，将文本传入
w.generate('and that government of the people, by the people, for the people, shall not perish from the earth.')

# 将生成的词云保存为output.png图片文件，导出到当前文件夹中
w.to_file('output.png')
```



`wordcloud`库为每一个词云生成一个WordCloud对象（注意，此处的W和C是大写）

也就是说，`wordcloud.WordCloud()`代表一个词云对象，我们将它赋值给`w`。

现在，这个`w`就是词云对象啦！我们可以调用这个对象。

我们可以在`WordCloud()`括号里填入各种参数，控制词云的字体、字号、字的颜色、背景颜色等等。

wordcloud库会非常智能地按空格进行分词及词频统计，出现次数多的词就大。



# 美化词云

## 2号词云：面朝大海，春暖花开（配置词云参数）

增加宽、高、字体、背景颜色等参数

```python
# 2号词云：面朝大海，春暖花开
# B站专栏：同济子豪兄 2019-5-23

import wordcloud

# 构建词云对象w，设置词云图片宽、高、字体、背景颜色等参数
w = wordcloud.WordCloud(width=1000,height=700,background_color='white',font_path='msyh.ttc')

w.generate('从明天起，做一个幸福的人。喂马、劈柴，周游世界。从明天起，关心粮食和蔬菜。我有一所房子，面朝大海，春暖花开')

w.to_file('output.png')
```

![2号词云：面朝大海，春暖花开](https://upload-images.jianshu.io/upload_images/13714448-0984e89b4a6d948b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果参数过多，第二行写成长长的一行不好看，可以写成多行，让代码更工整

```python
# 2号词云：面朝大海，春暖花开
# B站专栏：同济子豪兄 2019-5-23

import wordcloud

# 构建词云对象w，设置词云图片宽、高、字体、背景颜色等参数
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc')

w.generate('从明天起，做一个幸福的人。喂马、劈柴，周游世界。从明天起，关心粮食和蔬菜。我有一所房子，面朝大海，春暖花开')

w.to_file('output.png')
```

## 常用参数

- width 词云图片宽度，默认400像素

- height 词云图片高度 默认200像素

- background_color 词云图片的背景颜色，默认为黑色

  `background_color='white'`

- font_step 字号增大的步进间隔 默认1号

  font_path 指定字体路径 默认None，对于中文可用`font_path='msyh.ttc'`

- mini_font_size 最小字号 默认4号

- max_font_size 最大字号 根据高度自动调节

- max_words 最大词数 默认200

- stop_words 不显示的单词 `stop_words={"python","java"}`
- Scale 默认值1。值越大，图像密度越大越清晰
- prefer_horizontal：默认值0.90，浮点数类型。表示在水平如果不合适，就旋转为垂直方向，水平放置的词数占0.9？
- relative_scaling：默认值0.5，浮点型。设定按词频倒序排列，上一个词相对下一位词的大小倍数。有如下取值：“0”表示大小标准只参考频率排名，“1”如果词频是2倍，大小也是2倍

- mask 指定词云形状图片，默认为矩形

  通过以下代码读入外部词云形状图片（需要先`pip install imageio`安装imageio）

```python
import imageio
mk = imageio.imread("picture.png")
w = wordcloud.WordCloud(mask=mk)
```

也就是说，我们可以这样来构建词云对象w，其中的参数均为常用参数的默认值，供我们自定义：

```python
w = wordcloud.WordCloud(      
    width=400,
    height=200,
    background_color='black',
    font_path=None, 
    font_step=1,
    min_font_size=4,
    max_font_size=None,
    max_words=200,
    stopwords={},
    scale=1,
    prefer_horizontal=0.9,
    relative_scaling=0.5,
    mask=None) 
```



# 从外部txt文件读入文本

## 3号词云：乡村振兴战略中央文件（句子云）

```python
# 3号词云：乡村振兴战略中央文件
# B站专栏：同济子豪兄 2019-5-23

import wordcloud

# 从外部.txt文件中读取大段文本，存入变量txt中
f = open('关于实施乡村振兴战略的意见.txt',encoding='utf-8')
txt = f.read()

# 构建词云对象w，设置词云图片宽、高、字体、背景颜色等参数
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc')

# 将txt变量传入w的generate()方法，给词云输入文字
w.generate(txt)

# 将词云图片导出到当前文件夹
w.to_file('output.png')

```



![3号词云：乡村振兴战略中央文件](https://upload-images.jianshu.io/upload_images/13714448-d1c528c24c6b554f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 中文分词

## 中文分词-第三方模块`jieba`

安装中文分词库jieba：在命令行中输入`pip install jieba`

打开python的`交互式shell`界面，也就是有三个大于号`>>>`的这个界面，依次输入以下命令。

```python
>>> import jieba
>>> textlist = jieba.lcut('同济大学的前身是1907年德国医生埃里希·宝隆在上海创办的德文医学堂')
>>> textlist
['同济大学', '的', '前身', '是', '1907', '年', '德国', '医生', '埃里希', '·', '宝隆', '在', '上海', '创办', '的', '德文', '医学', '堂']
>>> string = " ".join(textlist)
>>> string
'同济大学 的 前身 是 1907 年 德国 医生 埃里希 · 宝隆 在 上海 创办 的 德文 医学 堂'
```

以上代码将一句`完整的中文字符串`转换成了`以空格分隔的词组成的字符串`，而后者是绘制词云时`generate()`方法要求传入的参数。

## 4号词云：同济大学介绍词云（中文分词）

```python
# 4号词云：同济大学介绍词云
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud和中文分词库jieba
import jieba
import wordcloud
# 构建并配置词云对象w
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc')

# 调用jieba的lcut()方法对原始文本进行中文分词，得到string
txt = '同济大学（Tongji University），简称“同济”，是中华人民共和国教育部直属，由教育部、国家海洋局和上海市共建的全国重点大学，历史悠久、声誉卓著，是国家“双一流”、“211工程”、“985工程”重点建设高校，也是收生标准最严格的中国大学之一'
txtlist = jieba.lcut(txt)
string = " ".join(txtlist)

# 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('output.png')
```

![4号词云：同济大学介绍词云](https://upload-images.jianshu.io/upload_images/13714448-825336d32a5f351a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 5号词云：乡村振兴战略中央文件（词云）

```python
# 5号词云：乡村振兴战略中央文件（词云）
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud和中文分词库jieba
import jieba
import wordcloud

# 构建并配置词云对象w
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc')

# 对来自外部文件的文本进行中文分词，得到string
f = open('关于实施乡村振兴战略的意见.txt',encoding='utf-8')
txt = f.read()
txtlist = jieba.lcut(txt)
string = " ".join(txtlist)

# 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('output.png')
```

![5号词云：乡村振兴战略中央文件(词云)](https://upload-images.jianshu.io/upload_images/13714448-37d2bfc5b048943d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





# 高级词云：绘制指定形状的词云

通过以下代码读入外部词云形状图片（需要先`pip install imageio`安装imageio）

```python
import imageio
mk = imageio.imread("picture.png")
w = wordcloud.WordCloud(mask=mk)
```

## 6号词云：乡村振兴战略中央文件（五角星形状）

```python
# 6号词云：乡村振兴战略中央文件（五角星形状）
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud和中文分词库jieba
import jieba
import wordcloud

# 导入imageio库中的imread函数，并用这个函数读取本地图片，作为词云形状图片
import imageio
mk = imageio.imread("wujiaoxing.png")
w = wordcloud.WordCloud(mask=mk)

# 构建并配置词云对象w，注意要加scale参数，提高清晰度
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc',
                        mask=mk,
                        scale=15)

# 对来自外部文件的文本进行中文分词，得到string
f = open('关于实施乡村振兴战略的意见.txt',encoding='utf-8')
txt = f.read()
txtlist = jieba.lcut(txt)
string = " ".join(txtlist)

# 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('output.png')
```

![6号词云：乡村振兴战略中央文件(五角星)](https://upload-images.jianshu.io/upload_images/13714448-5e0428a99a988454.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 7号词云：新时代中国特色社会主义（中国地图形状）

```python
# 7号词云：新时代中国特色社会主义（中国地图形状）
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud和中文分词库jieba
import jieba
import wordcloud

# 导入imageio库中的imread函数，并用这个函数读取本地图片，作为词云形状图片
import imageio
mk = imageio.imread("chinamap.png")
w = wordcloud.WordCloud(mask=mk)

# 构建并配置词云对象w，注意要加scale参数，提高清晰度
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc',
                        mask=mk,
                        scale=15)

# 对来自外部文件的文本进行中文分词，得到string
f = open('新时代中国特色社会主义.txt',encoding='utf-8')
txt = f.read()
txtlist = jieba.lcut(txt)
string = " ".join(txtlist)

# 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('output.png')
```

加scale参数为15的效果

![7号词云：新时代中国特色社会主义(中国地图形状)](https://upload-images.jianshu.io/upload_images/13714448-66c774c3013bd7dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

不加scale参数的效果，稍显模糊

  ![中国地图词云](https://upload-images.jianshu.io/upload_images/13714448-002e6bc0085c0bd0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 8号词云：三国演艺词云（stopwords参数去除词）

```python
# 8号词云：三国演艺词云（去掉曹操和孔明）
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud和中文分词库jieba
import jieba
import wordcloud

# 导入imageio库中的imread函数，并用这个函数读取本地图片，作为词云形状图片
import imageio
mk = imageio.imread("chinamap.png")
w = wordcloud.WordCloud(mask=mk)

# 构建并配置词云对象w，注意要加stopwords集合参数，将不想展示在词云中的词放在stopwords集合里
w = wordcloud.WordCloud(width=1000,
                        height=700,
                        background_color='white',
                        font_path='msyh.ttc',
                        mask=mk,
                        scale=15,
                        stopwords={'曹操','孔明'})

# 对来自外部文件的文本进行中文分词，得到string
f = open('threekingdoms.txt',encoding='utf-8')
txt = f.read()
txtlist = jieba.lcut(txt)
string = " ".join(txtlist)

# 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('output21.png')

```



![三国演艺词云](https://upload-images.jianshu.io/upload_images/13714448-9644b496af2d874b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 9号词云：哈姆雷特（勾勒轮廓线）

```python
# 9号词云：哈姆雷特（勾勒轮廓线）
# B站专栏：同济子豪兄 2019-5-23

# 导入词云制作库wordcloud
import wordcloud

# 将外部文件包含的文本保存在text变量中
string = open('hamlet.txt').read()

# 导入imageio库中的imread函数，并用这个函数读取本地图片，作为词云形状图片
import imageio
mk = imageio.imread("alice.png")

# 构建词云对象w，注意增加参数contour_width和contour_color设置轮廓宽度和颜色
w = wordcloud.WordCloud(background_color="white",
                        mask=mk,
                        contour_width=1,
                        contour_color='steelblue')

# # 将string变量传入w的generate()方法，给词云输入文字
w.generate(string)

# 将词云图片导出到当前文件夹
w.to_file('aliceoutput.png')
```

![8号词云：哈姆雷特(勾勒轮廓线)](https://upload-images.jianshu.io/upload_images/13714448-4372015a5f588812.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 进阶词云：尽享数据驱动与开源社区



## 9号词云：绘制你的微信好友个性签名词云

```python
# 9号词云：绘制你的微信好友个性签名词云
# B站专栏：同济子豪兄 2019-05-23

# 导入微信库ichat，中文分词库jieba
import itchat
import jieba

# 先登录微信，跳出登陆二维码
itchat.login()
tList = []
# 获取好友列表
friends = itchat.get_friends(update=True)

# 构建所有好友个性签名组成的大列表tList
for i in friends:
    # 获取个性签名
    signature = i["Signature"]
    if 'emoji' in signature:
        pass
    else:
        tList.append(signature)
text = " ".join(tList)

# 对个性签名进行中文分词
wordlist_jieba = jieba.lcut(text, cut_all=True)
wl_space_split = " ".join(wordlist_jieba)

# 导入imageio库中的imread函数，并用这个函数读取本地图片，作为词云形状图片
import imageio
mk = imageio.imread("chinamap.png")

# 导入词云制作库wordcloud
import wordcloud

# 构建并配置词云对象w，注意要加scale参数，提高清晰度
my_wordcloud = wordcloud.WordCloud(background_color='white',
                                   width=1000,
                                   height=700,
                                   font_path='msyh.ttc',
                                   max_words=2000,
                                   mask=mk,
                                   scale=20)
my_wordcloud.generate(wl_space_split)

nickname = friends[0]['NickName']
filename = "{}的微信好友个性签名词云图.png".format(nickname)
my_wordcloud.to_file(filename)

# 显示词云图片
import matplotlib.pyplot as plt
plt.imshow(my_wordcloud)
plt.axis("off")
plt.show()
print('程序结束')
```

![微信好友个性签名词云](https://upload-images.jianshu.io/upload_images/13714448-f0c63277bed6e336.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 情感分析词云





# 课后闲话

## wordcloud库

[wordcloud的Github主页](<https://github.com/amueller/word_cloud>)<br>

## 词云绘制的原理

[python123：你不知道的词云](<https://python123.io/tutorials/word_cloud>)<br>

## 词云制作微信小程序

![词云制作微信小程序](https://upload-images.jianshu.io/upload_images/13714448-d2f670f92db778fb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# `赞赏码`

![子豪兄的赞赏码](https://upload-images.jianshu.io/upload_images/13714448-bec288cb077c7f08.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





# 文本及图片素材

- 《哈姆雷特（英文版）》全文:<https://python123.io/resources/pye/hamlet.txt><br>

- 《三国演义》全文:<https://python123.io/resources/pye/threekingdoms.txt><br>

- 《新时代中国特色社会主义》全文:<https://python123.io/resources/pye/%E6%96%B0%E6%97%B6%E4%BB%A3%E4%B8%AD%E5%9B%BD%E7%89%B9%E8%89%B2%E7%A4%BE%E4%BC%9A%E4%B8%BB%E4%B9%89.txt><br>
- 《关于实施乡村振兴战略的意见》全文:<https://python123.io/resources/pye/%E5%85%B3%E4%BA%8E%E5%AE%9E%E6%96%BD%E4%B9%A1%E6%9D%91%E6%8C%AF%E5%85%B4%E6%88%98%E7%95%A5%E7%9A%84%E6%84%8F%E8%A7%81.txt><br>



![chinamap.png](https://upload-images.jianshu.io/upload_images/13714448-1cf1651ab5697142.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![wujiaoxing.png](https://upload-images.jianshu.io/upload_images/13714448-289890b06087cacc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![communicate.png](https://upload-images.jianshu.io/upload_images/13714448-1d98aa21535c7336.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![manshape1.png](https://upload-images.jianshu.io/upload_images/13714448-fbdb0725750e61ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![manshape2.png](https://upload-images.jianshu.io/upload_images/13714448-870c1eda4853fc76.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![puzzle.png](https://upload-images.jianshu.io/upload_images/13714448-24833eaaeb38dbbc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![weixinlogo.png](https://upload-images.jianshu.io/upload_images/13714448-d5e0c0412744ee23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![woman1.png](https://upload-images.jianshu.io/upload_images/13714448-ec1462b9738876b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![woman2.png](https://upload-images.jianshu.io/upload_images/13714448-425014720b69840d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![womanshape3.png](https://upload-images.jianshu.io/upload_images/13714448-8a4e6c43165ed7e0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 参考资料与扩展阅读

[翻译：WorldCloud()官方使用说明 & matplotlib.pyplot.imshow()官方使用说明](<https://blog.csdn.net/htuhxf/article/details/80471442>)<br>

[Python语言程序设计MOOC 北京理工大学 嵩天](<https://www.icourse163.org/learn/BIT-268001#/learn/announce>)<br>

[python123：你不知道的词云](<https://python123.io/tutorials/word_cloud>)<br>

