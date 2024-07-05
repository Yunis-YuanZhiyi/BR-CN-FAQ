> Tags: #ACOPOS_P3 #多摩川 #T_Format #编码器

- [1 033ACOPOS P3控制多摩川编码器电机的使用说明](#_1-033acopos-p3%E6%8E%A7%E5%88%B6%E5%A4%9A%E6%91%A9%E5%B7%9D%E7%BC%96%E7%A0%81%E5%99%A8%E7%94%B5%E6%9C%BA%E7%9A%84%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E)
- [2 概述](#_2-%E6%A6%82%E8%BF%B0)
- [3 硬件、软件配置说明](#_3-%E7%A1%AC%E4%BB%B6%E8%BD%AF%E4%BB%B6%E9%85%8D%E7%BD%AE%E8%AF%B4%E6%98%8E)
	- [3.1 测试硬件配置](#_31-%E6%B5%8B%E8%AF%95%E7%A1%AC%E4%BB%B6%E9%85%8D%E7%BD%AE)
	- [3.2 测试软件版本信息](#_32-%E6%B5%8B%E8%AF%95%E8%BD%AF%E4%BB%B6%E7%89%88%E6%9C%AC%E4%BF%A1%E6%81%AF)
	- [3.3 编码器卡固件版本](#_33-%E7%BC%96%E7%A0%81%E5%99%A8%E5%8D%A1%E5%9B%BA%E4%BB%B6%E7%89%88%E6%9C%AC)
- [4 实现方式](#_4-%E5%AE%9E%E7%8E%B0%E6%96%B9%E5%BC%8F)
	- [4.1 配置方式](#_41-%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)
		- [4.1.1 使用P3自带编码接口配置步骤](#_411-%E4%BD%BF%E7%94%A8p3%E8%87%AA%E5%B8%A6%E7%BC%96%E7%A0%81%E6%8E%A5%E5%8F%A3%E9%85%8D%E7%BD%AE%E6%AD%A5%E9%AA%A4)
		- [4.1.2 使用外接编码器卡配置步骤](#_412-%E4%BD%BF%E7%94%A8%E5%A4%96%E6%8E%A5%E7%BC%96%E7%A0%81%E5%99%A8%E5%8D%A1%E9%85%8D%E7%BD%AE%E6%AD%A5%E9%AA%A4)
	- [4.2 手动修改参数表（供参考）](#_42-%E6%89%8B%E5%8A%A8%E4%BF%AE%E6%94%B9%E5%8F%82%E6%95%B0%E8%A1%A8%EF%BC%88%E4%BE%9B%E5%8F%82%E8%80%83%EF%BC%89)
	- [4.3 编码器多圈溢出警告问题处理](#_43-%E7%BC%96%E7%A0%81%E5%99%A8%E5%A4%9A%E5%9C%88%E6%BA%A2%E5%87%BA%E8%AD%A6%E5%91%8A%E9%97%AE%E9%A2%98%E5%A4%84%E7%90%86)
- [5 FAQ](#_5-faq)
	- [5.1 7022/7038 报错](#_51-70227038-%E6%8A%A5%E9%94%99)
	- [5.2 7058/7013/7038报错](#_52-705870137038%E6%8A%A5%E9%94%99)
	- [5.3 Error 67](#_53-error-67)
	- [5.4 7065报错](#_54-7065%E6%8A%A5%E9%94%99)
	- [5.5 多摩川编码器警告、报警位说明](#_55-%E5%A4%9A%E6%91%A9%E5%B7%9D%E7%BC%96%E7%A0%81%E5%99%A8%E8%AD%A6%E5%91%8A%E6%8A%A5%E8%AD%A6%E4%BD%8D%E8%AF%B4%E6%98%8E)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 033ACOPOS P3控制多摩川编码器电机的使用说明

# 2 概述

- ACP10 V5.8.0 版本及以上， ACOPOS P3 的如下硬件模块：
    - 8EAC0150.001-1   V2.2.0.4 版本及以上
    - 8EAC0150.003-1   V2.2.0.4 版本及以上
    - 8EIxxxxxxxx.xxxx-x 其必须带有D0或更高版本的8ZECxxx
    - （例如8EI8X8HWT10.xxxx-1  V2.3.0.3版本及以上）
- 固件版本链接：
    - [V4.1 HW Upgrade (8EAC0150.001-1) | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/downloads/software/automation-studio/hw-upgrades/v41-hw-upgrade-8eac0150001-1/?noredirect=1)
    - [V4.1 HW Upgrade (8EAC0150.003-1) | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/downloads/software/automation-studio/hw-upgrades/v41-hw-upgrade-8eac0150003-1/?noredirect=1)
    - [V4.0 HW Upgrade (8EI8X8HWT10.xxxx-1) | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/downloads/software/automation-studio/hw-upgrades/v40-hw-upgrade-8ei8x8hwt10xxxx-1/?noredirect=1)
- 🔴注：以上硬件模块仅支持5V供电的多摩川编码器电机，目前不支持12V多摩川编码器电机。
- 可以支持日本多摩川(Tamagawa) 以下分辨率的编码器：
    - 16 bit 多圈, 17 bit 单圈（eg.TS5700N8500、TS5667N420、TS5667N253..etc）
    - 16 bit 多圈, 23 bit 单圈（eg.TS5700N8420..etc）
- 本文为ACOPOS P3控制多摩川编码器电机的使用说明，主要测试ACOPOS P3带TS5700N8500型号多摩川绝对值编码器电机的功能。

# 3 硬件、软件配置说明

## 3.1 测试硬件配置

- 贝加莱硬件
    - PLC控制器： X20CP1584
    - 伺服驱动器：Acopos P3 8EI2X2MWD10.0700-1
    - 外扩编码器卡型号：8EAC0150.001-1
- 翡叶动力（第三方）多摩川编码器的电机
    - 电机：5FSRA44-300E31KB0-0
    - 编码器型号：多摩川绝对值编码器TS5700N8500(16 bit 多圈, 17 bit 单圈)
    - 编码器电缆型号：5FSCE0020.30-53I(02)
- 编码器电缆接口如图：
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705214841476.png)
- 注： 编码器需要接入3.6V外接电池，不推荐无外接电池。
- 若不接入3.6V外接电池，将有如下影响：
    - A）主电源切断后，编码器不能实现超速检测和过载检测功能，也不能保存编码器数据。
    - B）每次ACOPOS P3寻参时，将出现编码器无电池报警，该报警不能清除，但不影响编码器正常使用
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705214929930.png)

## 3.2 测试软件版本信息

- Automation Studio：AS4.6.2.116
- Automation Runtime: E4.61
- Visual Components: V4.62.0
- ACP10 ARNC0(Motion): 5.8.0

## 3.3 编码器卡固件版本

- ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215155247.png)
- 🔴注：如选用外扩编码器卡，其需要2.2.0.4版本或更高，而ACOPOS P3固件版本可低于图中本次测试的2.3.0.2版本。

# 4 实现方式

- ACOPOS P3控制多摩川编码电机共有两种实现方式：
    - <span style="background:#A0CCF6">1___</span>使用P3自带编码器的接口控制（ACOPOS P3 encoder interface X4x）
    - <span style="background:#A0CCF6">2___</span>使用外扩编码器模块的接口控制（8EAC0150.00x-1）

## 4.1 配置方式

- 使用自带编码器接口与使用外扩编码器接口的配置步骤如下。选用编码器卡时，应注意其供电电压应与多摩川编码器供电电压相匹配。

### 4.1.1 使用P3自带编码接口配置步骤

- P3驱动器自带编码器接口配置选择T-Format类型，选择使用自带编码器卡
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215347585.png)
- 由于软件硬件版本的不同（原因未知），配置自带编码器接口的界面时，没有T-Format的选项。此时，先配置自带编码器接口之后再使用SPT参数表配置自带编码器相关参数,如下：
    - 带编码器接口配置界面：
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215412262.png)
    - SPT参数表配置界面：
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215448395.png)
        - 参数说明：
            - ParID:97，编码器类型。
            - ParID:887，编码器多圈范围。
            - ParID:109，编码器单圈精度，此参数设置不对，电机不能正常使用。
            - ParID:1556，编码器接口供电电压。P3上自带的编码器接口卡默认为12V供电，使用时需根据实际编码器供电电压设置。
            - ParID:1390，编码器通讯波特率。
            - ParID:727，编码器的ENCOD_LINE_CHK_IGNORE写16，即忽略多摩川编码器多圈溢出警告（ACP10V5.13及其以后版本有此更新）
            - M1为同步电机的电机参数。
            - 请注意各个参数顺序不能有误。

### 4.1.2 使用外接编码器卡配置步骤

- 驱动器配置中禁用自带编码器卡，选择使用外扩编码器卡
    - （本次测试使用的TS5700N8500多摩川编码器为5V供电，因此需要使用5V供电的外扩编码器卡，型号为8EAC0150.001-1（one encoder interface））
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215652777.png)
- 外扩编码器卡配置中选择T-Format类型
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215712776.png)
    - 注：本测试选用8EAC0150.001-1型号外扩编码器。若选用8EAC0150.003-1型号，该编码器卡同样支持T-Format类型，并且可分别选择3个接口的编码器类型
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215733074.png)

## 4.2 手动修改参数表（供参考）

- 若当使用的编码器分辨率不符合上述两种支持的编码器范围，可尝试通过改写轴的参数表的方式实现编码器正常运行（类似于使用自带编码器接口无法选择T-Format的情况，详情见 4.1章节 ）步骤如下：
- <span style="background:#F0A7D8">1___</span>禁用所有编码器卡
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215829852.png)
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215839876.png)
- <span style="background:#F0A7D8">2___</span>手动写入轴的参数表
    - 根据选择不同的编码器卡硬件，选择对应的编码器参数ID。因采用外扩编码器卡，参数表应写入ENCODE2的相关参数。若出现7065报错，处理方式见5.4 7065错误
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705215926266.png)
    - 注：注意参数表顺序不能有误。
- 通过以上两种方法配置完成后，添加LibACP10MC_SingleAx_ST单轴控制例程，对电机进行测试。
- <span style="background:#A0CCF6">A___</span>Test测试
    - 程序下载完成后，打开轴的Test，Initialize→Switch on，电机上电，无报错。给出Positive、Negative正、反转命令，电机能够正常工作。
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220034306.png)
- <span style="background:#A0CCF6">B___</span>程序测试
    - 通过Toolbox在程序中添加LibACP10MC_SingleAx_ST单轴控制例程。
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220059022.png)
- <span style="background:#A0CCF6">C___</span>通过程序中的BasicControl发送命令，电机能够正常运行。
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220134634.png)

## 4.3 编码器多圈溢出警告问题处理

- 当编码器总圈数超过最大圈数时，会有39030: Encoder: Warning bit is set和39059: Encoder: Status message，info：Status code = 8警告，如下图：
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220203368.png)
- 溢出警告示意图
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220230230.png)
- 该警告不影响电机正常使用，但是如果被触发后只能手动使用719（Encoder command）参数置1复位该警告，如果不719置1，任何home操作后都会重新显示此警告。如果不想显示则需配置一下ParID 727参数为16（ACP10 V5.13及以后版本可用），即忽略多摩川编码器多圈溢出警告。
- 目前使用ACP10 V5.13 版本，实测此问题已经被解决
- 实际使用中因为不知道实际编码器圈数信息，建议配置727参数为16，减少麻烦。

# 5 FAQ

## 5.1 7022/7038 报错

- 原因：在TEST窗口，或Network Command Trace 中出现该报错，表示驱动器无法检测编码器信号。
- 处理方式：
    - 1.检查Automation Runtime，ACP版本和固件版本及软件配置是否正确。
    - 2.检查编码器电缆接线端子是否匹配正确。
- ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220421717.png)
- ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220444354.png)

## 5.2 7058/7013/7038报错

- 原因：Switch on后出现该报错，表示编码器出现故障，例如没有接外部3.6V电源或外部电源有过掉电。
- 处理方式：检查外部电源的接线是否准确，然后通过写入ParID: ENCOD2_CMD值为1，复位该报警。
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220535605.png)

## 5.3 Error 67

- ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220553281.png)
- 原因：Switch on后出现该报错，表示电机参数表中63号参数磁偏角有误或者无效。
- 处理方式：第一次识别多摩川编码器电机时，需要**检测电机正确的磁偏角**。步骤如下:
    - <span style="background:#A0CCF6">1___</span>在参数表中改变motor_phasing模式
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220628942.png)
    - <span style="background:#A0CCF6">2___</span>发送Determine parameters命令，检测磁偏角参数
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220725374.png)
    - <span style="background:#A0CCF6">3___</span>约20s后，参数表中返回磁偏角数值
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220801923.png)
    - <span style="background:#A0CCF6">4___</span>将参数手动更新到电机参数表中
        - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220821980.png)
    - <span style="background:#A0CCF6">5___</span>重新下载程序

## 5.4 7065报错

- 原因： Switch on或Home后出现该报错，表示编码器卡类型无效。
    - ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705220907547.png)
- 处理方式：检查编码器卡配置中选择的编码器类型是否准确，在此应选择为T-Format，且自带编码器已禁用。

## 5.5 多摩川编码器警告、报警位说明

- 原因：编码器内部有警告或者错误，此时须知道status code的具体数值，便于定位此错误，常见的多摩川编码器警告、报警位说明如下
- ![](FILES/033ACOPOS%20P3控制多摩川编码器电机的使用说明/image-20240705221000324.png)

# 6 更新日志

| 日期         | 修改人        | 修改内容   |
| :--------- | :--------- | :----- |
| 2020-12-10 | PXY<br>SDW | 初次创建   |
| 2024-07-05 | YZY        | 文档更新整理 |
