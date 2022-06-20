# ACOPOSinverter是否能用施耐德同规格的变频器替代
## 问题描述
ACOPOSinverter故障，是否能拆下通讯卡，并插入施耐德同规格的变频器替代？

## 解决方案
使用X2X或者POWERLINK接口的ACOPOSinverter的固件为B&R定制，原变频器上的X2X或者POWERLINK接口卡不能运行在非B&R固件的变频器上。所以这些变频器是无法使用施耐德同规格型号替换。
而使用CANOpen通讯的型号，则可以使用施耐德同规格型号替代。