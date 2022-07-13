# 002EPlan导致AS注册报错License operations cannot be performed.
## 问题描述
E-plan导致AS注册报错
Message: License operations cannot be performed. CodeMeter service might not be started.
BR.AS.License.Core.LicenseManager.BR.TechnologyGuarding.Interfaces.ILicenseManager.GetAvailableLicesns()
## 截图
![Img](./FILES/002EPlan导致AS注册报错License%20operations%20cannot%20be%20performed..md/img-20220713152117.png)

## 触发原因与解决方式
| 序号 | 反馈内容 | 解决方案 |
| -- | -- | -- |
| 1 | E-plan导致AS注册报错 | 当电脑安装了盗版的ePLAN,会引起AS无法运行。可以把C:\Windows\System32\drivers 里的multikey.sys改名字multikey.sysbak或剪切到其他地方。当使用完AS，或者需要使用ePLAN时候，把文件放回来或者改回原来名字即可。也许需要重启电脑，才能正常使用ePLAN。 |
| 2 | 没有安装EPLAN软件，没有对AS软件的安装卸载做任何操作，在使用过程中仍爆出此错误。 | 重启电脑即恢复正常 |
| 3 | 客户电脑内没有安装CodeMeter | 安装新版CodeMeter后解决 |
| 4 | -- | -- |