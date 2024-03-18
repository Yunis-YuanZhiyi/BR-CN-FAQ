> Tags: #DTM #X20EM1611 #X67DS438A

- [1 082AS导入X67DS438A报错DTM ID or list index not found](#1%20082AS%E5%AF%BC%E5%85%A5X67DS438A%E6%8A%A5%E9%94%99DTM%20ID%20or%20list%20index%20not%20found)
- [2 原因分析](#2%20%E5%8E%9F%E5%9B%A0%E5%88%86%E6%9E%90)
- [3 解决方式](#3%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#4%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B01.082-AS导入X67DS438A报错DTM ID or list index not found

- 报错信息
    - Error connecting DTM deviceX67DS438A'.(DTM ID or list index not found.Parameter name: dtmld)
- 试图将硬件配置从一个项目复制到另一个项目，复制成功了。
- 之后，将一个 X67DS438A 模块移动到另一条 X2X line上。之后，看到了错误信息 "Error connecting DTM device "X67DS438A (DTM ID or list index not found. Parameter name: dtmId". 目前无法从 Toolbox 中再次插入 X67-DS 模块。
- 使用版本
    - AS4.12.4.107SP
- ![](FILES/082AS导入X67DS438A报错DTM%20ID%20or%20list%20index%20not%20found/image-20240202221453661.png)

# 2 原因分析

- 在项目中安装任何 IO-Link 传感器/执行器之前，问题就已经存在。
- 在项目中安装 X67DS438A 并将其连接到 X2X line时，问题就会出现。我们现在要检查的是以下文件是否有问题。
- `\Physical\Config1\X20EM1611\DTM\X67DS438A`

# 3 解决方式

- 将AS项目中 `\Physical\Config1\X20EM1611\DTM\` 文件夹删除并从另一个项目中重新导入后，恢复正常。

# 4 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2024-02-02 | YZY | 初次创建 |
