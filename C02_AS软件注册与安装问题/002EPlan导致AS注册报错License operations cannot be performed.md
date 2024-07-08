- [1 002EPlan导致AS注册报错License operations cannot be performed.](#_1-002eplan%E5%AF%BC%E8%87%B4as%E6%B3%A8%E5%86%8C%E6%8A%A5%E9%94%99license-operations-cannot-be-performed)
- [2 问题描述](#_2-%E9%97%AE%E9%A2%98%E6%8F%8F%E8%BF%B0)
- [3 截图](#_3-%E6%88%AA%E5%9B%BE)
- [4 触发原因与解决方式](#_4-%E8%A7%A6%E5%8F%91%E5%8E%9F%E5%9B%A0%E4%B8%8E%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [5 原因](#_5-%E5%8E%9F%E5%9B%A0)
- [6 解决方法 1](#_6-%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-1)
- [7 解决方法 2](#_7-%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-2)
- [8 解决方法 3](#_8-%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95-3)
	- [8.1 找到 codeMeter 的 log 文件](#_81-%E6%89%BE%E5%88%B0-codemeter-%E7%9A%84-log-%E6%96%87%E4%BB%B6)
	- [8.2 将文件夹 logs 压缩打包发给 codeMeter 的德国技术支持中心](#_82-%E5%B0%86%E6%96%87%E4%BB%B6%E5%A4%B9-logs-%E5%8E%8B%E7%BC%A9%E6%89%93%E5%8C%85%E5%8F%91%E7%BB%99-codemeter-%E7%9A%84%E5%BE%B7%E5%9B%BD%E6%8A%80%E6%9C%AF%E6%94%AF%E6%8C%81%E4%B8%AD%E5%BF%83)

# 1 002EPlan导致AS注册报错License operations cannot be performed.

# 2 问题描述

- E-plan导致AS注册报错
- Message: License operations cannot be performed. CodeMeter service might not be started.
- BR.AS.License.Core.LicenseManager.BR.TechnologyGuarding.Interfaces.ILicenseManager.GetAvailableLicesns()

# 3 截图

- ![Img](./FILES/002EPlan导致AS注册报错License%20operations%20cannot%20be%20performed..md/img-20220713152117.png)

# 4 触发原因与解决方式

| 序号  | 反馈内容                                        | 解决方案                                                                                                                                                         |
| --- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | E-plan导致AS注册报错                              | 当电脑安装了盗版的ePLAN,会引起AS无法运行。可以把C:\Windows\System32\drivers 里的multikey.sys改名字multikey.sysbak或剪切到其他地方。当使用完AS，或者需要使用ePLAN时候，把文件放回来或者改回原来名字即可。也许需要重启电脑，才能正常使用ePLAN。 |
| 2   | 没有安装EPLAN软件，没有对AS软件的安装卸载做任何操作，在使用过程中仍爆出此错误。 | 重启电脑即恢复正常                                                                                                                                                    |
| 3   | 客户电脑内没有安装CodeMeter                          | 安装新版CodeMeter后解决                                                                                                                                             |

# 5 原因

- 通常 AS 安装的时候会自动安装好相关的配合驱动，其中有一个是关于 License 注册的。我们的 AS 注册用到的是一个叫威步（WIBU）的公司的解决方案，一般我们装好 AS 就没问题了，不用操心这个东西。但是如果没办法启动 codeMeter 服务的话，你可以按照下面几个步骤尝试解决。

# 6 解决方法 1

- 不能启动的原因之一有可能是软件版本不匹配，WIBU 的官网，找到下载安装包，重新单独安装。
- 下载链接如下：
    - http://codemeter.com/us/service/downloads.html
- 下图为该链接网页，选择红框内的文件，下载并安装。安装后重启电脑，然后再重新注册 AS 就可以了。
    - ![](FILES/002EPlan导致AS注册报错License%20operations%20cannot%20be%20performed/image-20221126234046590.png)

# 7 解决方法 2

- 可以先尝试查找一下system32目录下是否有以下文件，如果能找到，请删除之后重启电脑再尝试
    - vusb.sys，vusbbox.sys，mutilkey.sys， mcamvusb.sys, vusbbus.sys
- 除此之外，kingsoftcrashdump.exe（金山 wps 崩溃排查工具）也会造成 CodeMeter 服务无法启动

# 8 解决方法 3

- 如果按照以上步骤依旧无法启动 codeMeter，有可能是因为客户的电脑上安装了一切其他的盗版软件（比如：epaln，eplan 的注册码也是和 WIBU 合作的，而有一些 eplan 的破解方式修改 codeMeter 的授权通道，让 eplan 绕过 codeMeter 直接开启。）如果是这个原因，那么再重装 codeMeter 也没办法打开AS。需要检查自己的电脑。
- 如何确定是哪一个软件影响了 codeMeter？可以按照如下步骤做。

## 8.1 找到 codeMeter 的 log 文件

- CodeMeter 在运行时有自己的 log 记录，可以到当时 codeMeter 的安装路径下去找，文件夹原本为隐藏文件，所以要在 windows 里面设置隐藏文件为可见。
    - ![](FILES/002EPlan导致AS注册报错License%20operations%20cannot%20be%20performed/image-20221126234254036.png)

## 8.2 将文件夹 logs 压缩打包发给 codeMeter 的德国技术支持中心

- Logs 这个文件夹里面都是你的记录（如下图），直接压缩后发送至邮箱 support@wibu.com。
    - ![](FILES/002EPlan导致AS注册报错License%20operations%20cannot%20be%20performed/image-20221126234329036.png)
- support 会回复告诉你你的电脑具体到底是哪一个路径什么文件有问题。
