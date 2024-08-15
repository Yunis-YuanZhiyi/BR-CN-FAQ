> Tags: #ACOPOS_6D

- [1 A06.007.在PC上编译ACOPOS 6D项目注意事项](#_1-a06007%E5%9C%A8pc%E4%B8%8A%E7%BC%96%E8%AF%91acopos-6d%E9%A1%B9%E7%9B%AE%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9)
- [2 所需软件与资料](#_2-%E6%89%80%E9%9C%80%E8%BD%AF%E4%BB%B6%E4%B8%8E%E8%B5%84%E6%96%99)
- [3 安装方式](#_3-%E5%AE%89%E8%A3%85%E6%96%B9%E5%BC%8F)
	- [3.1 mapp 6D软件包](#_31-mapp-6d%E8%BD%AF%E4%BB%B6%E5%8C%85)
	- [3.2 HWX文件_ACOPOS 6D控制器配置文件](#_32-hwx%E6%96%87%E4%BB%B6_acopos-6d%E6%8E%A7%E5%88%B6%E5%99%A8%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)
- [4 AS版本与mapp6D组件版本版本匹配要求](#_4-as%E7%89%88%E6%9C%AC%E4%B8%8Emapp6d%E7%BB%84%E4%BB%B6%E7%89%88%E6%9C%AC%E7%89%88%E6%9C%AC%E5%8C%B9%E9%85%8D%E8%A6%81%E6%B1%82)
- [5 更新日志](#_5-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 A06.007.在PC上编译ACOPOS 6D项目注意事项

- 在项目维护过程中，我们往往不需要对ACOPOS 6D Controller进行固件更新等操作，我们仅需要使用Automation Studio，即可更新ACOPOS 6D的控制部分程序。
- 此文档主要提及在此过程中在Automation Studio软件环节，需要进行的软件安装等准备操作。

# 2 所需软件与资料

| 类别         | 文件名                           | 用处        | 更新频率   |
| ---------- | ----------------------------- | --------- | ------ |
| mapp 6D软件包 | AS4_TP_mapp6D_1.11.7000.6.exe | AS项目控制软件包 | 大约每三个月 |
| HWX file   | 8YFLM01.0000.00I.zip          | 硬件通信配置文件  | 保持不变   |
| AS软件       | AS4.12                        | AS软件      | 保持不变   |

> 🔴 注意：mapp 6D 1.x 版本 2.x 版本，均只支持在AS 4下使用。mapp 6D 6.x 才支持AS 6下开发。
> 🔴 注意：使用mapp 6D 1.x 与 2.x 的项目下，只能使用mappMotion控制轴，不能使用ACP10。

# 3 安装方式

## 3.1 mapp 6D软件包

- <span style="background:#A0CCF6">1___</span>获取最新的软件安装包
- <span style="background:#A0CCF6">2___</span>打开Automation Studio软件，点击 Tool → Upgrades → Local → 选择 mapp6D 安装包安装
    ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240814162629315.png)

## 3.2 HWX文件_ACOPOS 6D控制器配置文件

- <span style="background:#A0CCF6">1___</span>获取方式 → 联系相关贝加莱技术人员获取硬件文件 8YFLM01.0000.00I
    - 解压后文件内容如下
    - ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815133512365.png)
- <span style="background:#A0CCF6">2___</span>复制 HWX 文件夹至AS安装文件夹
    - 要正确添加硬件文件，必须找到 Automation Studio 安装文件夹。
    - `{ AS 安装文件夹 }/BrAutomation/{ AS 版本 }/AS/Hardware/Modules`
    - ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815140204219.png)
- <span style="background:#A0CCF6">3___</span>复制 HWX文件至 `C:\ProgramData\BR\AS412\Hardware\Modules`
    - 其中AS412为使用的AS软件文件夹
    - ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815141228663.png)
    - 🚨若没有拷贝，则有可能出现如下报错
        - 在硬件图示页面中 6D 显示变白
        - 编译报错固件地址错误，提示 6801
        - ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815140900479.png)
- <span style="background:#A0CCF6">4___</span>打开AS软件，右键PLK口，即可添加此6D控制器
    - ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815141655638.png)

# 4 AS版本与mapp6D组件版本版本匹配要求

- 每一版本mapp6D的要求均有不同，见下表
- ![undefined](FILES/007在PC上编译ACOPOS%206D项目注意事项/image-20240815141859523.png)

# 5 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-08-14 | YZY<br>QHC | 初次创建 |
