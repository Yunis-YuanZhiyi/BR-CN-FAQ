# 了解OPC UA Server被多少Client连接
- 通过UA Expert，可以了解到实际连接的Client的相关信息
- ![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202161625394.png)
- 通过上图可知有三个Client同时连接同一个Server，上图中显示为一台名为CNSHAN745的电脑，通过UaExpert软件，通过访问opc.tcp//10.86.13.114:4840此链接访问了此OPC UA Server。
- 
## 举例说明
- ![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202162111645.png)

- ![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202162405576.png)

# 了解OPC UA Server被多少Session连接
- 为避免OPC UA资源消耗过大，系统默认设置Session可使用数量为50，若多Client多数据点位连接，需要注意Session消耗数量，并合理调整OPC UA Server的相关参数
- ![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202163142183.png)
我们可以通过以下相关参数了解当前OPC UA的资源消耗信息

OPC UA服务器名称空间中的一些nodeid值得用来诊断调试。
```
NodeID
        0:i=2285
BrowserPath
        0:Objects/0:Server/0:ServerDiagnostics/0:ServerDiagnosticsSummary/0:CurrentSubscriptionCount
说明
        Current subscription count
```

```
NodeID
        0:i=2277
BrowserPath
        0:Objects/0:Server/0:ServerDiagnostics/0:ServerDiagnosticsSummary/0:CurrentSessionCount
说明
        Current session count
```

```
NodeID
        0:i=2259
BrowserPath
        0:Objects/0:Server/0:ServerStatus/0:State
说明
        Server state
```

所有 OPC UA 通信都是通过会话( Session )完成的，在正常情况下，会话必须始终处于活动状态。服务器和客户端都可以监视会话的状态，以便它们能够及早发现问题，并且可以执行适当的清理，即使会话未正确关闭。
一个Client可以发起多个Session连接Server，Server只能知道被多少个Session连接，但不知道有多少个Client数量连接

![](028如何知道OPC%20UA%20Server被多少Client连接.svg)

## 实际获取一个OPC UA Server当前被多少Session访问数
![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202104038139.png)

