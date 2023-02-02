UA Server namespace
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

# 实际获取一个OPC UA Server当前被多少Session访问数
![](FILES/028如何知道OPC%20UA%20Server被多少Client连接/image-20230202104038139.png)

