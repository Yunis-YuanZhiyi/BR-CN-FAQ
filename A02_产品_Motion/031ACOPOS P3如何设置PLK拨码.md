- [背景](#%E8%83%8C%E6%99%AF)
- [使用 `8EAD0000.000-1` 显示模块进行拨码](#%E4%BD%BF%E7%94%A8%20%608EAD0000.000-1%60%20%E6%98%BE%E7%A4%BA%E6%A8%A1%E5%9D%97%E8%BF%9B%E8%A1%8C%E6%8B%A8%E7%A0%81)
	- [一、将显示模块插入 ACOPOS P3 的 X9 口](#%E4%B8%80%E3%80%81%E5%B0%86%E6%98%BE%E7%A4%BA%E6%A8%A1%E5%9D%97%E6%8F%92%E5%85%A5%20ACOPOS%20P3%20%E7%9A%84%20X9%20%E5%8F%A3)
	- [二、模块上电后基本介绍](#%E4%BA%8C%E3%80%81%E6%A8%A1%E5%9D%97%E4%B8%8A%E7%94%B5%E5%90%8E%E5%9F%BA%E6%9C%AC%E4%BB%8B%E7%BB%8D)
	- [三、设置拨码](#%E4%B8%89%E3%80%81%E8%AE%BE%E7%BD%AE%E6%8B%A8%E7%A0%81)
- [使用动态节点分配方案 dynamic node allocation (DNA) 拨码](#%E4%BD%BF%E7%94%A8%E5%8A%A8%E6%80%81%E8%8A%82%E7%82%B9%E5%88%86%E9%85%8D%E6%96%B9%E6%A1%88%20dynamic%20node%20allocation%20(DNA)%20%E6%8B%A8%E7%A0%81)

# 背景

- ACOPOS P 3 是作为通过 POWERLINK 协议与贝加莱 PLC / APC 进行通信的，每一台 ACOPOS P 3 设备均需要分配一个独立的站点号以区分驱动不同的设备。
- ACOPOS P 3 硬件上没有拨码盘，且每台设备的默认的 PLK 拨码均为 0，因此需要使用如下方式进行拨码
    - 1. 使用 `8EAD0000.000-1` 显示模块进行拨码
    - 2. 在 AS 中使用动态节点分配方案 dynamic node allocation (DNA) 来实现自动拨码

> 如果 ACOPOS P3 8EI 伺服驱动器的供电电压为 24 VDC，且其节点编号设置为 0，则 LED "PLK "亮红灯。

# 使用 `8EAD0000.000-1` 显示模块进行拨码

- 模块外观如下
    - ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827224052195.png)

## 一、将显示模块插入 ACOPOS P3 的 X9 口

> 此模块允许热插拔

- 将此显示模块插在 X9 端口上
![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827230417189.png)

- 为了将显示模块 8EAD0000.000-1 能正常安装，在 ACOPOS P3 模块上方至少需要 100 mm 的间隙；
- ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827234853342.png)

## 二、模块上电后基本介绍

- 显示模块 8 EAD 配有四个键，根据显示的信息执行不同的命令。相应的命令显示在显示模块上显示的屏幕的底部。
    - ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827224243224.png)
- 模块启动后
- 启动程序后（持续时间约 5 秒），将显示启动屏幕。它包含 8EAD 显示模块所连接模块的相关信息：
- ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827224948004.png)

> ⭐即可检查当前设备的节点号是否设置正确

## 三、设置拨码

- <span style="background:#F0A7D8">1. </span>按下 `左 1` 键，进入菜单页
- ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827235714966.png)
- 显示屏显示主菜单，此时第一个选项“Node Number”应该高亮，如未高亮，使用 `右二 Up键` 或 `右一 Down键` 按钮移动光标直至其被选中
- <span style="background:#F0A7D8">2. </span>确认第一个选项“Node Number”高亮，按 `左一 Show键` 进入拨码设置
- ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230828001320732.png)
- <span style="background:#F0A7D8">3. </span>反复按 `右二 Up建`，直到数字达到所需数值。
- <span style="background:#F0A7D8">4. </span>按 `右一 Next键` 跳转到节点编号的下一位。
- 重复步骤 **3** 和 **4**，直到节点编号的每个数字都达到所需的值。
- <span style="background:#F0A7D8">5. </span>应用/不应用节点编号
    - <span style="background:#F0A7D8">A. </span>应用节点编号并退出菜单选项 "Node number 节点编号"：
        - 按 `左一 Set键`
        - 伺服驱动器断电上电
        - ⚠️新设置的节点编号**只有在重新启动** ACOPOS P 3 伺服驱动器后**才会应用**。
    - B. 不应用节点编号并退出 "Node number 节点编号" 菜单选项：
        - 按 `左二 Back键`
        - 新的节点编号设置不会应用。主菜单重新显示在显示屏上。

# 使用动态节点分配方案 dynamic node allocation (DNA) 拨码

- 项目里 ACOPOS P3的站点号是配置为01
- ![](FILES/031ACOPOS%20P3如何设置PLK拨码/image-20230827223717162.png)
- 系统上电，建立通讯并传输完成 acp10sys 后，ACOPOS P3的站点号变为01.
