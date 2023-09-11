# 简要帮助描述信息
- 触发功能库
    - AsMbTCP
- 错误代码常量名
    - MbERR_STATION_NOT_CONNECTED
- 简要描述
    - Modbus 站点未连接
- 错误详细描述
    - 特定的需要连接的 Modbus 站未能建立链接
- 建议解决方式
    - 检查通信

# PLC 作 Master，PC 使用模拟器作 Slave
- **现象**
    - 1586 PLC 做了通信测试。其中 PLC 作为 master，电脑用软件模拟了 slave。
    - 用仿真实现了通信，但是实物通信一直起不来，报错 34201，找不到站点。
    - 换了别人的电脑也可以用
- **原因**
    - 防火墙问题
    - 如下修改即可
    - ![](FILES/34201%20mbERR_STATION_NOT_CONNECTED/image-20230911192154383.png)
