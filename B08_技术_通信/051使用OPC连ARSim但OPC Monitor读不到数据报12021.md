# 051使用OPC连ARSim但OPC Monitor读不到数据报12021

# 现象

- `PVI connect error. ErrNo: 12021. Connection name: @/Pvi/LNINA2/ARsim_TCPIP1/Station/Automatic ARSim connection`
- 到 CPU 这一层就连不上了
- OPC Server 是在 PC 上
- ![](FILES/051使用OPC连ARSim但OPC%20Monitor读不到数据报12021/image-20231012133316201.png)

# Log 信息如何获取

- OPC 使用的报错信息是在 log 里面记录的，可以在 PVI 软件安装的路径下的 Bin 文件夹下能看到
- 例如 `D:\AS\PVI\V4.6\Bin` 目录下，可见 `BR.OPC.Server.log` 文件
- ![](FILES/051使用OPC连ARSim但OPC%20Monitor读不到数据报12021/image-20231012135409179.png)

# 原因

- CPU name 那里默认的名字有空格导致的，和报错 12021 就对应
- ![](FILES/051使用OPC连ARSim但OPC%20Monitor读不到数据报12021/image-20231012133231072.png)
