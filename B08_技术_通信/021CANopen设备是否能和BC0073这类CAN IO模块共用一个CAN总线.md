# CANopen设备是否能和BC0073这类CAN IO模块共用一个CAN总线
## 问题描述
CANopen设备是否能和BC0073这类CAN IO模块共用一个CAN总线？

## 解决方案
不支持BC0073模块；支持其他CAN IO模块，但是要在AS中将CAN的configuration里的Use CANopen compliant CAN identifiers 设置为ON

![Img](./FILES/021CANopen设备是否能和BC0073这类CAN%20IO模块共用一个CAN总线.md/img-20220620101118.png)
![Img](./FILES/021CANopen设备是否能和BC0073这类CAN%20IO模块共用一个CAN总线.md/img-20220620101124.png)

