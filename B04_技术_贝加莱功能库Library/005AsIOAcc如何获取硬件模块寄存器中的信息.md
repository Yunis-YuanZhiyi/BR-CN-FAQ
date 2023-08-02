- [信息获取](#%E4%BF%A1%E6%81%AF%E8%8E%B7%E5%8F%96)
- [如何操作](#%E5%A6%82%E4%BD%95%E6%93%8D%E4%BD%9C)
	- [以 AsIOAccRead 为例读 `X20SD1207` 模块温度](#%E4%BB%A5%20AsIOAccRead%20%E4%B8%BA%E4%BE%8B%E8%AF%BB%20%60X20SD1207%60%20%E6%A8%A1%E5%9D%97%E6%B8%A9%E5%BA%A6)

# 需求

- 当我们想了解贝加莱模块的状态信息，我们通常通过在线监测此模块 I/O mapping 的信息，例如
- ![](FILES/005AsIOAcc如何获取硬件模块寄存器中的信息/image-20230802235823978.png)
- 但当我们想更深入获取此模块内部的一些详细信息，我们可以从哪里获取？

# 信息获取

- 我们可以通过查找此模块相关的帮助信息，找到 Register description 的 Channel list
- ![](FILES/005AsIOAcc如何获取硬件模块寄存器中的信息/image-20230803000230277.png)
- 此章节的信息即是此模块还可以访问获取与设置的模块信息

# 如何操作

- 我们可以使用 AsIOAcc 功能块，来实现此效果
- ![](FILES/005AsIOAcc如何获取硬件模块寄存器中的信息/image-20230803000553798.png)

## 以 AsIOAccRead 为例读 `X20SD1207` 模块温度

- 功能块接口信息
- ![](FILES/005AsIOAcc如何获取硬件模块寄存器中的信息/image-20230803000632452.png)
- `pDeviceName` 的信息对应着模块当前的地址
    - 例如 `X20SD1207` 模块在硬件树中的位置如下，其地址就是 `IF6.ST1`
    - ![](FILES/005AsIOAcc如何获取硬件模块寄存器中的信息/image-20230803001030210.png)
- `pChannelName` 的信息对应着此模块 Register description 的 Channel list 表中的 Channel name
    - 比如我们想要读温度，那此名称即为 `Diag1_Temp`
- StructureText 代码的写法如下
```
AsIOAccRead_0.enable := TRUE;
AsIOAccRead_0.pDeviceName := ADR('IF6.ST1');  //’IF6.ST1’为模块当前的地址
AsIOAccRead_0.pChannelName := ADR('Diag1_Temp');
AsIOAccRead_0();

AsIOAccRead_0.value; //此数值即为温度数值
```
