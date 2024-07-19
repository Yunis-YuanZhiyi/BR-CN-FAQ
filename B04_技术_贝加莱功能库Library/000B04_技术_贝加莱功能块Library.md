- [1 B04_技术_贝加莱功能块Library](#_1-b04_%E6%8A%80%E6%9C%AF_%E8%B4%9D%E5%8A%A0%E8%8E%B1%E5%8A%9F%E8%83%BD%E5%9D%97library)
- [2 📥如何导入与使用](#_2-%E5%A6%82%E4%BD%95%E5%AF%BC%E5%85%A5%E4%B8%8E%E4%BD%BF%E7%94%A8)
- [3 ⭐功能池](#_3-%E5%8A%9F%E8%83%BD%E6%B1%A0)
	- [3.1 通信_CANopen_ArCAN](#_31-%E9%80%9A%E4%BF%A1_canopen_arcan)
	- [3.2 通信_CANopen_CAN_Lib](#_32-%E9%80%9A%E4%BF%A1_canopen_can_lib)
	- [3.3 系统检查_IECCheckY](#_33-%E7%B3%BB%E7%BB%9F%E6%A3%80%E6%9F%A5_iecchecky)
	- [3.4 通用功能_BrRand](#_34-%E9%80%9A%E7%94%A8%E5%8A%9F%E8%83%BD_brrand)
	- [3.5 文件读写_LxMpFile](#_35-%E6%96%87%E4%BB%B6%E8%AF%BB%E5%86%99_lxmpfile)
	- [3.6 画面显示_ECharts + mappView](#_36-%E7%94%BB%E9%9D%A2%E6%98%BE%E7%A4%BA_echarts--mappview)

# 1 B04_技术_贝加莱功能块Library

- [001Automation Studio（AS）梯形图LD编辑环境中如何调用函数库？](001Automation%20Studio（AS）梯形图LD编辑环境中如何调用函数库？.md)
- [002Automation Studio（AS）中，如何寻找Safetydesigner的库？](002Automation%20Studio（AS）中，如何寻找Safetydesigner的库？.md)
- [003如何通过程序获取硬件上的序列号](003如何通过程序获取硬件上的序列号.md)
- [004AS有什么功能块可以读到当前PLC型号吗](004AS有什么功能块可以读到当前PLC型号吗.md)
- [005AsIOAcc如何获取硬件模块寄存器中的信息](005AsIOAcc如何获取硬件模块寄存器中的信息.md)
- [FileIO_AR通过CIFS访问windows共享文件夹](../B02_技术_AutomationRuntime/010AR通过CIFS访问windows共享文件夹.md)
- [008计时器TON使用方式](008计时器TON使用方式.md)

# 2 📥如何导入与使用

- [006贝加莱库导入方式](006贝加莱库导入方式.md)

# 3 ⭐功能池

## 3.1 通信_CANopen_ArCAN

- 下载链接
    - [基于CAN口实现CANopen主站 | 使用ArCAN库 | 2018-11-29](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/DEMO-CANopen-ArCAN-Master-AS43-2018-11-29.zip ':ignore')
- 版本要求
    - `> =` AS3.09
- 适用范围
    - 有CAN口模块：X20IF2772，X20CS1070

## 3.2 通信_CANopen_CAN_Lib

- 下载链接
    - [基于CAN口实现CANopen主从站 | 使用CAN_Lib库 | 2013-03-07](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/DEMO-CAN-CANopen-Master-Slave-AS309-Demo-2013-03-07.zip ':ignore')
- 版本要求
    - `> =` AS4.3
- 适用范围
    - 有CAN口模块：X20IF2772，X20CS1070

## 3.3 系统检查_IECCheckY

- 下载链接
    - [系统检查 | IECCheckY库，动态检查IEC61131-3代码数组越界与除零等异常 | 2023-12-28](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/DEMO-IECCheckY-2023-12-28.zip ':ignore')
- 版本要求
    - `> =` AS3.09
- 适用范围
    - 所有

## 3.4 通用功能_BrRand

- 📋功能说明
    - [功能说明 | 随机数生成功能BrRand](007随机数生成功能BrRand.md)
- 🗃️下载链接
    - [通用功能 | BrRand库，动态生成随机数 | 2021-09-24](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/BrRand-2021-09-24.zip ':ignore')
- 版本要求
    - `> =` AR V3.06
- 适用范围
    - 所有

## 3.5 文件读写_LxMpFile

- 📋功能说明
    - 基于mappServices的MpRecipeXml功能进行简化封装，一个功能块，任意复杂的结构体，数据存储至XML文件，从XML文件将数据加载至数据中，支持数据加密。
    - 库版本: V1.00.8
    - [LxMpFile使用.pdf](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/LxMpFile使用.pdf ':ignore')
- 🗃️下载链接
    - [2024-07-07-LxMpFile.zip](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/2024-07-07-LxMpFile.zip ':ignore')

## 3.6 画面显示_ECharts + mappView

- [048mappView与ECharts配合显示动态可视化图表库](/B05_技术_mapp/048mappView与ECharts配合显示动态可视化图表库.md)
