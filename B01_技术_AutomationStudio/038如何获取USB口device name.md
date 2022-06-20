# 如何获取USB口device name
## 问题描述
如何获取USB口device name
## 解决方案
自从AR版本4.X起，USB 口device name 不是以前的IFX.STX形式，而是变成自动生成名字的。因此需要通过ASUSB这个库区获取device name。
具体步骤如下：
1.添加sample LibAsUSB1_ST

![Img](./FILES/038如何获取USB口device%20name.md/img-20220620094325.png)
![Img](./FILES/038如何获取USB口device%20name.md/img-20220620094339.png)

2. 在设备上插上U盘，下载后监控下图四个变量，将start_reading_data 手动置一，devcie_name 就是你要获取的名字。为了确保程序正常运行，你可以观察step的变化，应该是从0-2-3-4-5-6-7-8-9-0按顺序变化的。证明case一圈跑下来没有问题，此时device_name获取到的名字是可信的。否则说明程序出错，device_name 不可信。

![Img](./FILES/038如何获取USB口device%20name.md/img-20220620094403.png)

下图就是start_reading_data 手动置一后，正常运行的结果，U盘的device name 是‘/bd0’

![Img](./FILES/038如何获取USB口device%20name.md/img-20220620094408.png)

## 问题描述
U盘名字是不是固定的？能不能直接在file device里写/bd0？如下图

![Img](./FILES/038如何获取USB口device%20name.md/img-20220620094512.png)

## 解决方案
如果你只有一个U盘，不管插到哪一个口，名字都是/bd0，为了方便，可以直接写。但是万一你有两个U盘，那就会变成一个是/bd0，一个是/bd16，可能会混乱，因此，为了项目的谨慎，建议每次都获取一下，然后再程序中用DevLinik。

AS Help 参考路径：Location ID 4.14.18.39.2.6