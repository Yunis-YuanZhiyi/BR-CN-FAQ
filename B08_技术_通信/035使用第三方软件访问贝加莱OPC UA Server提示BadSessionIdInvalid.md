# 现象
- 使用C#代码实现OPC UA Client，访问贝加莱OPC UA Server的多个变量，有时部分节点通信没有响应报错
- 有时C#代码会返回以下报错信息，提示BadSessionIdInvalid
- ![](FILES/035使用第三方软件访问贝加莱OPC%20UA%20Server提示BadSessionIdInvalid/image-20230301171832579.png)

# 原因
- 因为贝加莱OPC UA Server默认同时允许访问的Session为50个
- ![](FILES/035使用第三方软件访问贝加莱OPC%20UA%20Server提示BadSessionIdInvalid/image-20230301172602155.png)
- 如果第三方设备连接访问，同时发起了超过50个Node访问，则会超过贝加莱Server允许的上限。
- ![](FILES/035使用第三方软件访问贝加莱OPC%20UA%20Server提示BadSessionIdInvalid/image-20230301172959010.png)

# 解决方式
- ![](FILES/035使用第三方软件访问贝加莱OPC%20UA%20Server提示BadSessionIdInvalid/image-20230301172040423.png)