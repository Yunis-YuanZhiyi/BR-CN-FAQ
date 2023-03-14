# X20BC0087 Watchdog超时后如何恢复
## 问题描述

在主站断开连接后，X0BC0087模块S/E出现红色闪烁，ModbusTCP Toolbox 看到如下状态，显示看门狗超时。
当重新连接主站后，主站发送读指令，可以正常读到数据。但使用写指令，操作失败，具体表现是BC0087模块后面的DO无法输出，此时模块依旧处于红色S/E闪烁。

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150323.png)

我尝试过在ModbusTCP ToolBox中使用Device Diagnosis，将其中的watchdog mode由默认的Trigger with each access改为Disable，模块可以恢复正常。

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150331.png)

按照ModbusTCP Toolbox的Help文档里面对于Trigger with each access的描述，主站对BC0087的进行读或者写操作都会复位模块的看门狗超时。

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150337.png)



## 解决方案

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150354.png)

通讯正常的时候watchdog的状态是C1，读写通道是会重置watchdog，但如果触发了time out后，watchdog的状态跳转到C2

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150411.png)
![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150417.png)

C2状态读写是无法重置watchdog的，需要在地址0x1044这个地址用6或者16功能码写193来将watchdog的状态恢复到C1，这时通讯才能正常工作。

![Img](./FILES/011X20BC0087%20Watchdog超时后如何恢复.md/img-20220617150425.png)
