# 用U盘更新包的方式给CPU烧卡
## 问题描述
之前有关于用U盘更新包（PIP）的方式给CPU烧卡的需求
例如客户在给数量很多的新CF卡或者新的1382类型CPU安装程序时，比较方便。

## 原因分析
X20系列CPU是带有板载的AR的，所以U盘烧卡是可以实现的。
如果没有AS，也可以用RUC看到板载的AR版本，

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144451.png)

## 解决方案

测试PLC：X20CP1584，X20CP3583 + CF卡（已格式化）
AS：4.5.3.86，4.3.3.196，4.2.10.53，

再4.5中直接使用AS中生成PIP的功能

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144504.png)

一般来说板载的AR版本都比较低（例如这里测试的CPU板载AR是J4.02），所以这里要更改选项

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144520.png)

在弹出的配置框中勾选Force initial installation

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144555.png)

或者勾选允许initial installation；
另外Identification里可以更改验证方式，防止误烧写。

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144609.png)

如果使用的是4.3或之前的版本，需要使用RUC来生成更新包
先生成RUC包

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144818.png)

在RUC中打开项目，生成更新包

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144845.png)

同样的，mode更改成AR<4.33；下面的选项中勾选强制初始化安装。
    
![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144852.png)

之后我又在4.2上做了测试，当然4.2也可以使用RUC来生成；
值得一提的是，4.2tools中的Create Remote Install Structure功能也可以直接生成可供烧卡的U盘更新包；

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144905.png)

这里并没有像RUC里AR<4.33的选项，所以直接输出到U盘就可以了。
另外也支持一些分区的选项。

![Img](FILES/036用U盘更新包的方式给CPU烧卡.md/img-20220617144914.png)
