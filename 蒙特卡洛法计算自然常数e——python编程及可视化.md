# 蒙特卡洛法计算自然常数e——python编程及可视化

> 张子豪  同济大学

蒙特卡洛方法是一种用野蛮粗暴的蛮力对抗精致数学的一种计算思维，能够将复杂数学问题转化为简单粗暴的重复步骤，在工程上有很多应用。我还用蒙特卡洛方法计算了圆周率，请看我另一篇博客。

![蒙特卡洛方法计算自然常数e](https://upload-images.jianshu.io/upload_images/13714448-0e73a7a806a876ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![蒙特卡洛方法计算自然常数e](https://upload-images.jianshu.io/upload_images/13714448-800677c161c98f44.gif?imageMogr2/auto-orient/strip)



# 原理

![曲面四边形面积即为积分之后的值](https://upload-images.jianshu.io/upload_images/13714448-89504a4f4ce5f7a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)原理：用蒙特卡洛方法随机在左图矩形方格中撒点，统计y=1/x内外点的个数，
由几何概型，估算出曲线下曲面四边形的面积。
同时，由定积分可算出这部分面积为ln2，即e**(估算出的面积)== 2，即可求出e。

撒点越多，e的计算值也越来越趋近2.71828的真实值。

# 源代码

```python
# 张子豪 2019-3-14
import random
import matplotlib.pyplot as plt
import numpy as np


DARTS = 1024*1024 # 总共撒点的个数
counts = 0 # 落在曲线下方的点数
e = 0 # e的计算值
xs = [0,0]
ys = [0,0]

# 开始画左边的图：撒点估计曲线下方的面积
plt.subplot(121)
x = np.arange(0.5,2.5,0.001)
plt.ylim(0,1.25) # y轴坐标范围
plt.xlabel('x') # x轴标签
plt.ylabel('y') # y轴标签
plt.plot(x,1/x) # 绘制反比例函数曲线
plt.legend(loc=1) # 在右上角增加图例
plt.legend(['y = 1 / x']) # 图例的内容
plt.plot([1,1,2,2],[0,1,1,0],'r',linewidth=0.2) # 绘制撒点范围框

for i in range(DARTS):
    x = random.uniform(1,2)
    y = random.uniform(0,1)
    if y < 1/x: # 点落在曲线下方
        counts += 1
        plt.subplot(121)
        plt.plot(x,y,'g.')
    else: # 点落在曲线上方
        plt.subplot(121)
        plt.plot(x,y,'r.')
    if counts>0:
        e = pow(2,i/counts)

    # 开始画右边的图：e的计算值随投掷次数的关系
    plt.subplot(122)
    xs[0] = xs[1] # 上一个e值与下一个e值，通过xs与ys列表中的两个元素进行两点连线
    xs[1] = i
    ys[0] = ys[1]
    ys[1] = e
    plt.ylim(0,4.5) # y轴坐标范围
    plt.xlabel('Number of try') # x轴标签
    plt.ylabel('Estimation of e') # y轴标签
    plt.yticks(np.arange(0,4.5,0.5)) # y轴刻度线
    plt.title('e:{:.10f}\ncount:{}'.format(e,i)) # 图的标题动态更新
    plt.axhline(np.e,linewidth=0.05,color='r') # 绘制2.71828参考线
    plt.plot(xs,ys,'b--',linewidth=0.3) # 绘制e的计算值随撒点次数变化的曲线
    plt.ion() # 保持图像处于交互更新状态 
    plt.pause(0.2) # 控制撒点速度
```



# 可视化

![蒙特卡洛方法计算自然常数e](https://upload-images.jianshu.io/upload_images/13714448-800677c161c98f44.gif?imageMogr2/auto-orient/strip)
