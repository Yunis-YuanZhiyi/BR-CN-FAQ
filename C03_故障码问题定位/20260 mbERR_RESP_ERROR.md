> Tags: #ModbusRTU

# 20260 mbERR_RESP_ERROR

- 简单文本
    - 接收到无效帧
- 错误描述
    - 接收到无效帧，协议错误。
- 纠错建议
    - 检查通信站或连接。
- 参考
    - [048使用RS232接转换器实现ModbusRTU通信](/B08_技术_通信/048使用RS232接转换器实现ModbusRTU通信.md)

# 案例一

- 现象
    - 一个IF1030模块通过modbus通讯读取1块电能表数据，后续做一个改造，在这个modbus通讯中再加入一个变频器作为通讯的从站，但是通讯程序修改之后报错20291
- 排查方式
    - <span style="background:#A0CCF6">1___</span>首先检测RS485接线是否正常，更换屏蔽双绞线，确认线路中的终端电阻都按照正确的方式连接。线路都确认正常后，仍然没有正常通讯。
    - <span style="background:#A0CCF6">2___</span>排查Slave正常，通过电脑使用测试软件modbus poll直接连接变频器，可以正确取去变频器终端数据
    - <span style="background:#A0CCF6">3___</span>重写modbusRTU通讯程序，直接和变频器通讯，报错20260
    - <span style="background:#A0CCF6">4___</span>按照第2步再一次通过PC抓包截取通讯数据如下：
        - ![](FILES/20291%20mbERR_FRM_READ/image-20240722175341025.png)
- 原因
    - 在Query Message中，请求读取的数据长度是2，而Response Message返回的数据长度是4；这个变频器默认请求数据长度是以Byte定义的，而返回数据长度是以Word定义的。
