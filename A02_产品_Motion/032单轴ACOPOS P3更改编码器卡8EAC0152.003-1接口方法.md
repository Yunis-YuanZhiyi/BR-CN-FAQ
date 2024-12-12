> Tags: #ACOPOS_P3

- [1 A02.032.单轴ACOPOS P3更改编码器卡8EAC0152.003-1接口方法](#_1-a02032%E5%8D%95%E8%BD%B4acopos-p3%E6%9B%B4%E6%94%B9%E7%BC%96%E7%A0%81%E5%99%A8%E5%8D%A18eac0152003-1%E6%8E%A5%E5%8F%A3%E6%96%B9%E6%B3%95)
- [2 解决方案](#_2-%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
- [3 参数数值](#_3-%E5%8F%82%E6%95%B0%E6%95%B0%E5%80%BC)
- [4 注意事项](#_4-%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9)
- [5 举例说明](#_5-%E4%B8%BE%E4%BE%8B%E8%AF%B4%E6%98%8E)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 A02.032.单轴ACOPOS P3更改编码器卡8EAC0152.003-1接口方法

- 使用单轴 ACOPOS P3，在 P3 上插一张 `8EAC0152.003-1` 的通信卡
    - ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831133923473.png)
- 电机编码器和外接编码器的接口都是 EnDat 2.1，均接在此 `8EAC0152.003-1` 卡上。希望实现第一个口用来接收电机的反馈，第二个口接收外部编码器的反馈。
- 在默认配置中，ACOPOS P 3 的 ENCODE 1 指向的是默认的 X41 端口，与实际需求不一致。
- ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831135648752.png)
- 在实际控制中，外部编码器做主轴，电机跟随外部编码器运动。

# 2 解决方案

- 软件版本支持：**ACP10 5.22**及以上版本。
- 帮助 Automation Help 4.12.3 中的路径如下
    - ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831155731897.png)
- 可查阅帮助中的说明，🔴注意若电脑安装的是默认的AS4.12.6以下的版本，此信息在默认的本地帮助信息中没有，需要再次更新2个GB的 [AS Help更新包](https://www.br-automation.com/zh/downloads/software/automation-studio/automation-studio-412/v412-help-upgrade-v412-help-english/) 才能在本机电脑的帮助上看到。
    - [🟢可以点击跳转 → 在线英文帮助中对应章节直接浏览更多信息](https://help.br-automation.com/#/en/4/ncsoftware%2Facp10_drivefunctions%2Fgeberschnittstelle%2Fallgemeines%2Fgeberschnittstellenzuordnung%2Fgeberschnittstellenzuordnung_.html)
- 单轴P3可以根据需要任意选择驱动器上的编码器接口，如下图所示。
    - ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831135013700.png)
- 使用 ParID ENCOD_HW_SELECT（1718）可以为编码器 1 选择硬件上的任一编码器接口。
- ParID ENCOD2_HW_SELECT(1719) 可以为编码器 2 选择硬件上的任一编码器接口。

# 3 参数数值

- P3驱动器上各个编码器接口的设定数值如下
    - ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831135212810.png)

# 4 注意事项

- 1 使用 ENCOD_HW_SELECT 的编码器接口的分配必须在编码器驱动程序启动之前进行。在使用 mapp Motion 时，扩展编码器卡的接口类型可以在硬件配置时设置。如果不使用 mapp Motion，外接编码器卡硬件配置中的接口类型必须被设置成 Not Used。
- ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831135100429.png)
- 2 只有 P3支持选择编码器接口的功能。
- 3 SafeMOTION 不支持该功能。
- 4 只有8EAC0150.xxx-x, 8EAC0151.xxx-x, 8EAC0152.xxx-x and 8EAC0122.xxx-x 支持该功能。
- 5 每个编码器接口只能被配置一次。

# 5 举例说明

- 现场使用的单轴ACOPOS P3，编码器卡是8EAC0152.003-1。
- 电机编码器类型是 EnDat 2.1,接到 X41N，外接编码器类型是 EnDat 2.1，接到 X42N。
- 最终参数表的设置如下：
    - ![](FILES/032单轴ACOPOS%20P3更改编码器卡8EAC0152.003-1接口方法/image-20230831135127279.png)
- 一定是先设置编码器选择，再设定编码器类型和相关参数。
- 如果顺序颠倒，驱动器报错 7097。

# 6 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2023-08-31 | XP  | 编写文档 |
