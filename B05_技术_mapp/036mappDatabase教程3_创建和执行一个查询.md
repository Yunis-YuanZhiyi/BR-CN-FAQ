## 学习目标
- 配置编辑
- ​添加与配置MpDatabaseQuery功能块
- ​测试此功能

## 预计学习时间
- ​5分钟 

## STEP 1 确认数据库 Table参数
-  ![image-20230523152806937](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523152806937.png)

## STEP 2 在 AS 软件中配置编辑
-  ![image-20230523153210304](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523153210304.png)


1. 确认 AS 软件配置中的 mpdatabasecore 文件中配置的参数与实际数据库的信息对应一致
    A. mpdatabasecore 的 FROM 参数，与数据库中 Table 名同名
    B. mpdatabasecore 的 Process variable 参数对应的成员变量名，与数据库中表列名完全一致
-  ![image-20230523153427977](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523153427977.png)

## STEP 3 贝加莱帮助探索
- 详细描述可在 Automation Help 对应位置了解
-  ![image-20230523153644749](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523153644749.png)
## STEP 4 添加与配置 MpDatabaseQuery
1. 双击：DatabaseMgmt 任务 
- ![image-20230523154951224](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523154951224.png)


1. 单击添加网络)按钮
-  ![image-20230523155307641](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523155307641.png)


1. 双击：MpDatabaseQuery
-  ![image-20230523155530696](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523155530696.png)


1. 点击OK按钮
-  ![image-20230523155558201](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523155558201.png)


1. 按下回车键
-  ![image-20230523155638551](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523155638551.png)


1. 点击 AddressContact 按钮
2. 将 gDatabaseCore 参数填入 MpLink 区域
3. 按下回车
-  ![image-20230523155723053](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523155723053.png)


1. 按下空格键 （用于跳转到 Enable 的引脚） 
2. 输入参数 1
3. 按下回车键
-  ![image-20230523161313373](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523161313373.png)


1. 选择 Name 引脚，点击 AddressContact 按钮
2. 输入‘SelectData’区域。
>注意：名称必须用单引号 `'`
3. 按下回车键
-  ![image-20230523161648861](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523161648861.png)


1. 程序中的 MpDatabaseQuery 的 Name 引脚参数与 mpdatabasecore 配置表中的 Name 完全一致。
-  ![image-20230523161723284](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523161723284.png)

## STEP 5 测试功能
1. 点击 Transfer 按钮，进行程序下载
-  ![image-20230523161801990](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523161801990.png)

1. 点击 Transfer 按钮
-  ![image-20230523161854483](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523161854483.png)

1. 点击 Monitor 监控图标
-  ![image-20230523162015292](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523162015292.png)

1. 单击 Execute
2. 写入 1
3. 按下回车键
-  ![image-20230523162032231](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523162032231.png)

1. 可见 gQualityData 结构体中数据被来自数据库中的数据更新
-  ![image-20230523181656652](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523181656652.png)

1. 运行的 Python 程序中可见具体的执行命令 
-  ![image-20230523181722688](FILES/036AltenbuchnerMappDatabase3-创建和执行一个查询/image-20230523181722688.png)
