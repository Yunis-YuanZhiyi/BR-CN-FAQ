> Tags: #DTM #AS

- [1 062AS软件编译编译提示DTM could not be loaded](#_1-062as%E8%BD%AF%E4%BB%B6%E7%BC%96%E8%AF%91%E7%BC%96%E8%AF%91%E6%8F%90%E7%A4%BAdtm-could-not-be-loaded)
- [2 现象一](#_2-%E7%8E%B0%E8%B1%A1%E4%B8%80)
	- [2.1 解决方式](#_21-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [3 现象二](#_3-%E7%8E%B0%E8%B1%A1%E4%BA%8C)
	- [3.1 解决方式](#_31-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)

# 1 062AS软件编译编译提示DTM could not be loaded

# 2 现象一

- ![](FILES/062AS软件编译编译提示DTM%20could%20not%20be%20loaded/image-20221208171337630.png)
- 4.11的程序，重装了4.12和4.11的DTM，还是报错

## 2.1 解决方式

- 重装AS 4.11软件

# 3 现象二

- 导入了一个 DTM 文件，但却无法将其连接到 IO-Link 接口。使用 X20DS438A 卡的项目甚至无法编译。
- ![](FILES/062AS软件编译编译提示DTM%20could%20not%20be%20loaded/image-20240628095823108.png)

## 3.1 解决方式

- 删除这个目录

```
C:\ProgramData\IO-Link
```
