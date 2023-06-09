## 学习目标
- 添加配置
- 配置 MpDatabaseCore
- 测试功能
## Step 1 添加 MpLink配置
1. 点击 Configure View，选择 mappServices，右键选择 Add Object
2. 在弹出框中点击搜索
3. 在输入栏输入 MpDatabase
4. 拖动 MpdatabaseCore 配置文件到 mappServices 文件夹

![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530082936542.png)
## Step 2 配置 MpDatabaseCore
1. 如下图所示配置 Database
2. 记住 MpLink 的名称，例如此处创建的 MpLink 名为 **gDatabaseCore**

![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530083439476.png)

3. 相关帮助信息可在 Automation Help 中查找获得
![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230609215241042.png)

## Step 3 添加任务并配置 MpDatabaseCore
1. 新建 DatabaseMgmt 任务，选择 Ladder Program。

![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230609215346311.png)

2. 声明一个类型为 MpDatabaseCore 的变量 
![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530083548042.png)

3. 在程序中插入 MpDatabase 功能块
![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530083608807.png)

4. 将 MpLink 引脚与配置文件中的 MpLink 对应

![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530083713991.png)
 5. 编译后在线 Transfer 下载
## Step 4 测试功能
- Transfer 后打开 Monitor，置位功能块的 Connect 引脚

- ![](FILES/035mappDatabase教程2_创建与数据库的连接/image-20230530084008911.png)

