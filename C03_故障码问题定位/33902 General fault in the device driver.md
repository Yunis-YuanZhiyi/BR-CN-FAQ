### 问题描述
使用X20IF10E1-1模块进行Profinet通信，站点数量多了之后报错33902，导致通信中断
更换模块后问题仍然存在

General fault in the device driver
NXPCI Error PutPacket：0x800C0016

![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215092857315.png)

![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215092902860.png)
### 解决方案
Data exchange time客户改过参数为20ms
改回10ms后解决
![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215093056947.png)

