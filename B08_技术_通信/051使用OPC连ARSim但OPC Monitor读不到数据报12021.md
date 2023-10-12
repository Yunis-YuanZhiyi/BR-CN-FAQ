# 051使用OPC连ARSim但OPC Monitor读不到数据报12021

# 现象

- `PVI connect error. ErrNo: 12021. Connection name: @/Pvi/LNINA2/ARsim_TCPIP1/Station/Automatic ARSim connection`
- 到 CPU 这一层就连不上了
- OPC Server 是在 PC 上
- ![](FILES/051使用OPC连ARSim但OPC%20Monitor读不到数据报12021/image-20231012133316201.png)

# 原因

- CPU name 那里默认的名字有空格导致的，和报错 12021 就对应
- ![](FILES/051使用OPC连ARSim但OPC%20Monitor读不到数据报12021/image-20231012133231072.png)
