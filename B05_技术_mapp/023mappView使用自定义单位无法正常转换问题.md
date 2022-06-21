# 023mappView使用自定义单位无法正常转换问题
## 问题描述

Help文档中有对mappView自定义单位的使用做详细说明，但是在实际使用中，很多工程师按照以上步骤依旧无法实现单位转换。（Help中位置，Guid：44d0ec19-3891-437d-aaa7-0dc2a0650b55）
比如PLC数值为0.0009，界面上显示0.9。（单位可以是Help中指定的物理量纲，已有单位见Help中位置，Guid：b6b763b0-bd37-4754-811c-1db598056468）


## 解决方案

Help文档中实现步骤1~3没有问题，主要问题在于，第4步操作中错误将OPC UA变量的单位定义选择了新的自定义单位，实际应选择原单位。

为了不容易出错，调整实现步骤如下：
1. OPC UA变量表中，设置目标变量的单位，这里注意一定设置为原单位（这是Help第4步中写错的地方）
2. .units文件中，添加自定义单位Common Code（不要和已有单位重复）
3. units文件中，添加自定义单位与原单位的对应关系（比例，偏移）
4. .units文件中，填写ReferenceUnitNameSpace和ReferenceUnitID，必须对照OPC UA表中目标变量单位的Namespace、Unit ID
5. 添加unit文本文件，填写的Unit ID是自定义单位的Unit ID（添加unit文本，不要添加local文本或者mapView文本）
6. 界面控件Unit属性设置。需要修改Namespace和Common Code，必须填写的是.units文件自定义单位本身（顶部）的Namespace，Common Code
7. 界面控件Value属性，binding连接目标变量时一定要选变量本身（node），而非value。

