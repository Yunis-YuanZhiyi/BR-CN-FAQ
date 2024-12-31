> Tags: #驱动器 #运动控制 #ACOPOS_D1

- [1 贝加莱经济型驱动器ACOPOS D1](#_1-%E8%B4%9D%E5%8A%A0%E8%8E%B1%E7%BB%8F%E6%B5%8E%E5%9E%8B%E9%A9%B1%E5%8A%A8%E5%99%A8acopos-d1)
	- [1.1 ACOPOS D1 驱动器外观](#_11-acopos-d1-%E9%A9%B1%E5%8A%A8%E5%99%A8%E5%A4%96%E8%A7%82)
	- [1.2 ACOPOS D1 配套电机外观](#_12-acopos-d1-%E9%85%8D%E5%A5%97%E7%94%B5%E6%9C%BA%E5%A4%96%E8%A7%82)
	- [1.3 ACOPOS D1 接线示例](#_13-acopos-d1-%E6%8E%A5%E7%BA%BF%E7%A4%BA%E4%BE%8B)
- [2 ACOPOS D1 选型手册](#_2-acopos-d1-%E9%80%89%E5%9E%8B%E6%89%8B%E5%86%8C)
- [3 ACOPOS D1 用户手册](#_3-acopos-d1-%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C)
- [4 ACOPOS D1 配置选择](#_4-acopos-d1-%E9%85%8D%E7%BD%AE%E9%80%89%E6%8B%A9)
	- [4.1 通信配置文件下载](#_41-%E9%80%9A%E4%BF%A1%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E4%B8%8B%E8%BD%BD)
	- [4.2 网线类型说明](#_42-%E7%BD%91%E7%BA%BF%E7%B1%BB%E5%9E%8B%E8%AF%B4%E6%98%8E)
	- [4.3 ACOPOS D1 驱动器固件](#_43-acopos-d1-%E9%A9%B1%E5%8A%A8%E5%99%A8%E5%9B%BA%E4%BB%B6)
	- [4.4 ACOPOS D1 版本变更信息](#_44-acopos-d1-%E7%89%88%E6%9C%AC%E5%8F%98%E6%9B%B4%E4%BF%A1%E6%81%AF)
- [5 ACOPOS D1 Studio相关文档](#_5-acopos-d1-studio%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3)
	- [5.1 ACOPOS D1 离线固件升级说明](#_51-acopos-d1-%E7%A6%BB%E7%BA%BF%E5%9B%BA%E4%BB%B6%E5%8D%87%E7%BA%A7%E8%AF%B4%E6%98%8E)
- [6 ACOPOS D1 常见问题](#_6-acopos-d1-%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
	- [6.1 ACOPOS D1 FAQ](#_61-acopos-d1-faq)
- [7 更新日志](#_7-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 贝加莱经济型驱动器ACOPOS D1

- ACOPOS D1是一款贝加莱于2024年推出的经济型伺服驱动器，通过POWERLINK协议与贝加莱系统无缝集成。

## 1.1 ACOPOS D1 驱动器外观

![](FILES/035贝加莱经济型驱动器ACOPOS%20D1/image-20240326181320953.png)

## 1.2 ACOPOS D1 配套电机外观

![](FILES/035贝加莱经济型驱动器ACOPOS%20D1/image-20240326181357732.png)

## 1.3 ACOPOS D1 接线示例

![](FILES/035贝加莱经济型驱动器ACOPOS%20D1/image-20240309192034884.png)

# 2 ACOPOS D1 选型手册

- [点击访问 → ACOPOS D1 产品选型手册_Rev 1.0.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20产品选型手册_Rev%201.0.pdf ':ignore')

# 3 ACOPOS D1 用户手册

- [点击访问 → ACOPOS D1 用户手册_V1.0.5.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20用户手册_V1.0.5.pdf ':ignore')

# 4 ACOPOS D1 配置选择

## 4.1 通信配置文件下载

- ⭐ACOPOS D1 唯一指定XDD文件 → <span style="background:#F0A7D8">1.0.0.4</span>
    - [FFFF0005_ACOPOS_D1_POWERLINK_Cia402_V1.0.0.4.xdd](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/FFFF0005_ACOPOS_D1_POWERLINK_Cia402_V1.0.0.4.xdd ':ignore')
- ⭐推荐使用 Automation Studio 4.12 版本
    - 如使用AS4.12以前的版本导入时提示报警，联系贝加莱技术支持解决

## 4.2 网线类型说明

- ⭐默认情况下，新发货的ACOPOS D1硬件的网线接口仅支持 <span style="background:#A0CCF6">交叉线</span>。
- 若有其他需求，请联系贝加莱销售，详情参考 [037ACOPOS_D1_平行线与交叉线通讯选择](037ACOPOS_D1_平行线与交叉线通讯选择.md)

## 4.3 ACOPOS D1 驱动器固件

> ⭐ 请根据型号查看驱动器输出电流：
> 1 kW 及小功率驱动器（输出电流为3.0A和4.5A）使用 **SingleBoard** 升级固件；
> 大功率驱动器(5.4A及以上）使用 **ControlBoard** 升级固件。
- 👍2024-12-30 版本
    - 1 kW 以上刷Control
        - [点击下载 → PowerlinkControlBoard_4.B.16.8.bin](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/PowerlinkControlBoard_4.B.16.8.bin ':ignore')
    - 1 kW 以下刷Single
        - [点击下载 → PowerlinkSingleBoard_4.B.16.8.bin](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/PowerlinkSingleBoard_4.B.16.8.bin ':ignore')
    - 4.B.16.8 修复问题
        - 追随误差上电连接的时候会出现相差一个伺服周期
    - 4.B.16.6 新支持特性
        - 新加方法：触发回原点驱动器不动作，直接返回原点回归完成，使用mappMotion需要用来跳过PLC上电运行前必须回原点的步骤
        - 支持模式6连续多次执行原点回归
    - 注意事项：只要是4.0 boot的驱动器都可以更新，2024年开始之后的驱动器都可以更新此版本。若不是4.0 boot，升级软件会弹出提示框。
- 2024-08-15 版本
    - 1 kW 以上刷Control
        - [点击下载 → PowerlinkControlBoard_4.8.15.5.bin](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/PowerlinkControlBoard_4.8.15.5.bin ':ignore')
    - 1 kW 以下刷Single
        - [点击下载 → PowerlinkSingleBoard_4.8.15.5.bin](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/PowerlinkSingleBoard_4.8.15.5.bin ':ignore')
    - 注意：不要使用4.8.15.3与4.8.15.4版本，请更新。
- 2024-06-25 版本
    - boot是4.0的非STO的驱动器可以更新
    - [点击前往下载 → ACOPOS_D1_固件_boot是4.0的非STO的驱动器可以更新](https://br-community.com/downloadDis/257)
        - 内置两个文件 PowerlinkControlBoard_4.5.30.1.Bin与PowerlinkSingleBoard_4.5.30.1.Bin 均刷一次，分别对应驱动器中两块板。

## 4.4 ACOPOS D1 版本变更信息

- [042ACOPOS D1版本变更信息](042ACOPOS%20D1版本变更信息.md)

# 5 ACOPOS D1 Studio相关文档

- ACOPOS D1 Studio软件下载
    - [⭐点击前往 → 贝加莱社区-下载中心 → 下载 ACOPOS D1 Studio V1.1.0.10 软件](https://br-community.com/downloadDis/301)
    - 历史版本
        - [点击前往 → 贝加莱社区-下载中心 → 下载 ACOPOS D1 Studio V1.0.0.3 软件](https://br-community.com/downloadDis/95)
        - [点击前往 → 贝加莱社区-下载中心 → 下载 ACOPOS D1 Studio V1.0.0.2 软件](https://br-community.com/downloadDis/69)
- [ACOPOS D1 伺服参数备份说明_20240308.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20伺服参数备份说明_20240308.pdf ':ignore')
- [ACOPOS D1总线 HDI接线说明.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1总线%20HDI接线说明.pdf ':ignore')
- 保存电机参数
    - [ACOPOS D1 电机适配说明参数保存到编码器_20240426.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20电机适配说明%20参数保存到编码器_20240426.pdf ':ignore')
    - [ACOPOS D1 电机适配说明参数保存到驱动本地_20240426.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20电机适配说明%20参数保存到驱动本地_20240426.pdf ':ignore')
    - [ACOPOS D1参数修改与保存技巧.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1参数修改与保存技巧.pdf ':ignore')
    - [ACOPOS D1 开启多圈参数写入说明_20241227.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20开启多圈参数写入说明_20241227.pdf ':ignore')
- 在线固件升级
    - [ACOPOS D1 伺服固件升级说明_20240308.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20伺服固件升级说明_20240308.pdf ':ignore')
- STO功能说明
    - [ACOPOS D1 伺服STO功能说明_20240407.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20伺服STO功能说明_20240407.pdf ':ignore')

## 5.1 ACOPOS D1 离线固件升级说明

- ACOPOS D1 系列驱动器多段固件升级软件
    - [点击前往 → 贝加莱社区-下载中心 → 下载 ACOPSO D1 固件升级软件](https://br-community.com/downloadDis/68)
- 使用说明
    - ⚠️驱动器boot在3.0和4.0的才可以使用离线升级
    - 查看boot版本：按住驱动器第三个键，通电开机，从屏幕上可看到
    - [ACOPOS D1 伺服离线固件升级说明（串口）20240308.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20伺服离线固件升级说明（串口）_20240308.pdf ':ignore')

# 6 ACOPOS D1 常见问题

- [036ACOPOS_D1_Err4位置超差](036ACOPOS_D1_Err4位置超差.md)
- [037ACOPOS_D1_平行线与交叉线通讯选择](037ACOPOS_D1_平行线与交叉线通讯选择.md)
- [039ACOPOS_D1_Err13错误复位](039ACOPOS_D1_Err13错误复位.md)
- [040ACOPOS_D1_电机空载运行时抖动](040ACOPOS_D1_电机空载运行时抖动.md)
- ACOPOS D1 报错 Err 25 → 更新驱动器 4.8.15.5 或 4.b.16.6 版本固件
- ACOPOS D1 报错 Err 20 → 更新驱动器 4.8.15.5 或 4.b.16.6 版本固件
- [ACOPOS D1 Err18报警说明_20241220.pdf](/A02_产品_Motion/FILES/035贝加莱经济型驱动器ACOPOS%20D1/ACOPOS%20D1%20Err18报警说明_20241220.pdf ':ignore')

## 6.1 ACOPOS D1 FAQ

- [038ACOPOS_D1_FAQ](038ACOPOS_D1_FAQ.md)

# 7 更新日志

| 日期         | 修改人        | 修改内容                                                                                                                                                       |
| :--------- | :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2024-03-09 | ZSY<br>YZY | 初次创建                                                                                                                                                       |
| 2024-03-26 | YZY        | 更新外观图                                                                                                                                                      |
| 2024-03-29 | ZSY<br>YZY | 保存电机参数 相关文档进行了更新，修正了操作步骤需要进入Fn-2后才能进入Fn-20                                                                                                                 |
| 2024-04-26 | ZSY<br>YZY | 更新ACOPOS D1 用户手册 V1.0.3<br>更新ACOPOS D1 Studio V1.00.3<br>更新ACOPOS D1 电机适配说明参数保存到编码器_20240426.pdf<br>更新ACOPOS D1 电机适配说明参数保存到驱动本地_20240426.pdf               |
| 2024-05-06 | HDH<br>YZY | 更新ACOPOS D1 选型手册 V1.0                                                                                                                                      |
| 2024-06-24 | ZSY<br>YZY | 更新ACOPOS D1相关报错信息与FAQ                                                                                                                                      |
| 2024-06-25 | ZSY<br>YZY | 更新ACOPOS D1驱动器固件                                                                                                                                           |
| 2024-07-18 | ZSY        | 更新ACOPOS D1用户手册V1.0.4版本<br>更新自整定需要先进入FN-2模式；<br>更新32位二进制数数值图例；<br>更新了6.4.5章节，移除1010h对象字典操作; <br>2.5章节更新，X5为POWERLINK口输入，X6为输出；<br>更改7.3.2 TH110、TH150安装尺寸图 |
| 2024-08-14 | ZSY<br>YZY | 更新选型说明                                                                                                                                                     |
| 2024-08-22 | YZY        | 新增版本变更信息                                                                                                                                                   |
| 2024-08-30 | YZY        | 补充ACOPOS D1 驱动器固件使用说明                                                                                                                                      |
| 2024-10-08 | ZSY<br>YZY | 更新4.8.15版本驱动器固件信息                                                                                                                                          |
| 2024-10-12 | ZSY        | 更新 ACOPOS D1 Studio V1.1.0.10 软件                                                                                                                           |
| 2024-10-18 | ZSY<br>YZY | 更新 ACOPOS D1总线 HDI接线说明.pdf 与 ACOPOS D1参数修改与保存技巧.pdf                                                                                                        |
| 2024-11-30 | YZY        | 更新驱动器固件4.B.16.6                                                                                                                                            |
| 2024-12-27 | ZSY<br>YZY | 更新 ACOPOS D1 Err18报警说明_20241220.pdf<br>更新 ACOPOS D1 开启多圈参数写入说明_20241227.pdf<br>更新 ACOPOS D1 用户手册_V1.0.5.pdf                                                |
| 2024-12-30 | ZSY<br>YZY | 更新 ACOPOS D1驱动器固件版本 PowerlinkSingleBoard_4.B.16.8.bin                                                                                                      |
