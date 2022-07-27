# 001AS打开报错Could not load file or assembly 
## 问题描述
AS打开报错

Could not load file or assembly 
TechnologyGuarding.Interface， Version=1.0.0.0, Culture=neutral, PublicKeyToken=null or one of its dependencies.
The System cannot find the file specified.

## 截图
![Img](./FILES/001AS打开报错Could%20not%20load%20file%20or%20assembly%20.md/img-20220713151104.png)

## 触发原因与解决方式
| 序号 | 反馈内容 | 备注 | 解决方案 |
| -- | -- | -- | -- |
| 1 | 用户卸载AS4.7后把文件夹删掉，再安装AS4.8后无法打开，codemeter服务正常 | 安装最新版的codemeter，问题仍无法解决 | 使用腾讯管家，在卸载AS后清理了系统，没有卸载codemeter，再重装后解决 |
| 2 | 在安装过AS的电脑上安装另一个版本AS时出现 | - | 一般是因为新安装的AS中TG的启动路径和环境变量中TG的启动路径不匹配，可以通过修改环境变量来解决，可搜索 “[TG] [AS启动Technology Guarding报错解决方法](https://gitee.com/yzydeer/BuR-FAQ/raw/master/B01_%E6%8A%80%E6%9C%AF_AutomationStudio/FILES/032AS%E5%90%AF%E5%8A%A8Technology%20Guarding%E6%8A%A5%E9%94%99%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95.md/AS%E5%90%AF%E5%8A%A8Technology%20Guarding%E6%8A%A5%E9%94%99%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95.pdf)” |
| 3 | 安装Target For Simulink 6.3.1之后，导致原先能够使用的Automation Sudio软件全部出现此问题 | -- | 基于“[TG] [AS启动Technology Guarding报错解决方法](https://gitee.com/yzydeer/BuR-FAQ/raw/master/B01_%E6%8A%80%E6%9C%AF_AutomationStudio/FILES/032AS%E5%90%AF%E5%8A%A8Technology%20Guarding%E6%8A%A5%E9%94%99%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95.md/AS%E5%90%AF%E5%8A%A8Technology%20Guarding%E6%8A%A5%E9%94%99%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95.pdf)”解决，将环境变量改回AS软件指向的地方 |
| 4 | AS安装前，电脑安装了桌面管理软件。打开AS时，出现如图错误 | 通过桌面打开AS时，AS的启动方式默认为非管理员方式启动。右键选择，管理员运行该软件，AS可正常启动。 | 在AS 属性-高级中，修改AS的启动方式为管理员启动，解决。 |
| 5 | -- | -- | 贝加莱官网Download -> Software -> Technology Guarding 下载Technology Guarding，重新安装 | 
| -- | -- | -- | -- | 
