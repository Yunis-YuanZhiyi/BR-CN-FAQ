# 013Automation Studio中如何通过配置将以太网口配置为modbus TCP master？
Tags：modbus tcp、主站
A： 
1.开启modbus tcp 的master功能
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012541.png)
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012545.png)

2.添加modbus tcp 从站
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012600.png)
注意站点位置，不要重复，这里的node号可以随便填写，但是必须唯一。modbus tcp最后找从站是以IP地址找的。
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012613.png)

3.打开配置
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012721.png)
3.1：配置通道，首先配置从站的IP地址和端口号。（下图为例，从站IP地址为192.168.0.12 ，TCP端口号为502）
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012732.png)
3.2配置block。每一个Block可以通过下拉框选择Function code。并且设定通讯的起始地址，传输长度等信息。然后这个Block下可以以Channel为单位设计通道。
![Img](./FILES/013Automation%20Studio中如何通过配置将以太网口配置为modbus%20TCP%20master？.md/img-20220530012741.png)
4.双击modbus tcp可以打开io mapping，配置成功。