> 007随机数生成功能BrRand

> Tags: #功能块

- [1 BrRand](#1%20BrRand)
	- [1.1 此库功能描述](#1.1%20%E6%AD%A4%E5%BA%93%E5%8A%9F%E8%83%BD%E6%8F%8F%E8%BF%B0)
	- [1.2 说明](#1.2%20%E8%AF%B4%E6%98%8E)
	- [1.3 测试用例说明](#1.3%20%E6%B5%8B%E8%AF%95%E7%94%A8%E4%BE%8B%E8%AF%B4%E6%98%8E)
- [2 系统要求](#2%20%E7%B3%BB%E7%BB%9F%E8%A6%81%E6%B1%82)
- [3 错误码信息](#3%20%E9%94%99%E8%AF%AF%E7%A0%81%E4%BF%A1%E6%81%AF)
- [4 更新与维护地址](#4%20%E6%9B%B4%E6%96%B0%E4%B8%8E%E7%BB%B4%E6%8A%A4%E5%9C%B0%E5%9D%80)

# 1 BrRand

- 该库实现了随机数自动生成，其中包括限定范围的随机数生成与字符串自动生成。可用于测试与仿真场景。

| 类别 | 下载链接 | 版本要求 | 适用硬件类别 |
| :--- | :--- | :--- | ---- |
| 通用功能 | [通用功能 \| BrRand库，动态生成随机数 \| 2021-09-24](/B04_技术_贝加莱功能库Library/FILES/000B04_技术_贝加莱功能块Library/BrRand-2021-09-24.zip ':ignore') | >= AR V3.06 | 所有 |

## 1.1 此库功能描述

| **函数名**        | **说明**                     | **使用方式:ST写法**                                          | **使用方式:C写法**                                           |
| ----------------- | ---------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| RandBOOL          | 输出BOOL随机数               | PV := RandBOOL();                                            | PV = RandBOOL();                                             |
| RandUSINT         | 输出USINT随机数              | PV := RandUSINT();                                           | PV = RandUSINT();                                            |
| RandSINT          | 输出SINT随机数               | PV := RandSINT();                                            | PV = RandSINT();                                             |
| RandUINT          | 输出UINT随机数               | PV := RandUINT();                                            | PV = RandUINT();                                             |
| RandINT           | 输出INT随机数                | PV := RandINT();                                             | PV = RandINT();                                              |
| RandUDINT         | 输出UDINT随机数              | PV := RandUDINT();                                           | PV = RandUDINT();                                            |
| RandDINT          | 输出DINT随机数               | PV := RandDINT();                                            | PV = RandDINT();                                             |
| RandREAL          | 输出REAL随机数               | PV := RandREAL();                                            | PV = RandREAL();                                             |
| RandLREAL         | 输出LREAL随机数              | PV := RandLREAL();                                           | PV = RandLREAL();                                            |
| RandRangeUnsigned | 设定范围产生无符号整型随机数 | PV := RandRangeUnsigned(5,200);                              | PV = RandRangeUnsigned(5,200);                               |
| RandRangeSigned   | 设定范围产生有符号整型随机数 | PV := RandRangeSigned(-10,10);                               | PV = RandRangeSigned(-10,10);                                |
| RandRangeReal     | 设定范围产生浮点类型随机数   | PV := RandRangeReal(0.8,1); 注意事项: 输入REAL类型数据范围为 (-2147483,2147483) | PV = RandRangeReal(0.8,1); 注意事项: 输入REAL类型数据范围为 (-2147483,2147483) |
| FB_RandString     | 生成随机字符串               | FB_RandString_0.pString := ADR(sString); FB_RandString_0.uStrLen := SIZEOF(sString); FB_RandString_0(); | FB_RandString_0.pString = (UDINT)&sString; FB_RandString_0.uStrLen = sizeof(sString); FB_RandString(&FB_RandString_0); |

## 1.2 说明

- 每个函数均是同步执行，一个周期得到一个结果，若调用次数过多，需注意负载增量。

## 1.3 测试用例说明

- ST测试用例：
    - 通过测试项目的 **t_BrRand** 任务，长期测试，通过测试用例，观察 **bAllResult** 的数值，此值为 **TRUE** 则意味着通过测试。
    - 此任务批量对各随机数函数的输出结果进行检查，可自行在末尾添加测试用例。
- C测试用例：
    - 举例在C语言下的使用方式。

# 2 系统要求

| **支持的操作系统** | SG4       |
| ------------------ | --------- |
| **操作系统要求**   | 至少V3.06 |
| **依赖库版本**     | sys_lib   |

# 3 错误码信息

- 此功能块各函数的返回值即为输出值，无错误码信息。

# 4 更新与维护地址

- brhelp.cn
  - https://www.brhelp.cn/#/B04_%E6%8A%80%E6%9C%AF_%E8%B4%9D%E5%8A%A0%E8%8E%B1%E5%8A%9F%E8%83%BD%E5%BA%93Library/000B04_%E6%8A%80%E6%9C%AF_%E8%B4%9D%E5%8A%A0%E8%8E%B1%E5%8A%9F%E8%83%BD%E5%9D%97Library
- bitbucket
  - [FB_RandomLib - Bitbucket (br-automation.com)](https://bitbucket.br-automation.com/projects/FIWW/repos/fb_randomlib/browse)
