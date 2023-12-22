> 33902 General fault in the device driver

> Tags: #PROFINET #X20IF10E1_1 #PROFIBUS_DP #X20IF1061_1

- [1 X20IF10E1-1模块PROFINET通信，站点数量多了报错33902](#1%20X20IF10E1-1%E6%A8%A1%E5%9D%97PROFINET%E9%80%9A%E4%BF%A1%EF%BC%8C%E7%AB%99%E7%82%B9%E6%95%B0%E9%87%8F%E5%A4%9A%E4%BA%86%E6%8A%A5%E9%94%9933902)
	- [1.1 问题描述](#1.1%20%E9%97%AE%E9%A2%98%E6%8F%8F%E8%BF%B0)
	- [1.2 解决方案](#1.2%20%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
- [2 PROFIBUS DP通信被变频器影响，通信中断](#2%20PROFIBUS%20DP%E9%80%9A%E4%BF%A1%E8%A2%AB%E5%8F%98%E9%A2%91%E5%99%A8%E5%BD%B1%E5%93%8D%EF%BC%8C%E9%80%9A%E4%BF%A1%E4%B8%AD%E6%96%AD)
	- [2.1 现象](#2.1%20%E7%8E%B0%E8%B1%A1)
	- [2.2 原因与解决方式](#2.2%20%E5%8E%9F%E5%9B%A0%E4%B8%8E%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)

# 1 X20IF10E1-1模块PROFINET通信，站点数量多了报错33902

## 1.1 问题描述

- 使用X20IF10E1-1模块进行Profinet通信，站点数量多了之后报错33902，导致通信中断
- 更换模块后问题仍然存在
- General fault in the device driver
- NXPCI Error PutPacket：0x800C0016
    - ![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215092857315.png)
    - ![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215092902860.png)

## 1.2 解决方案

- Data exchange time客户改过参数为20ms
- 改回10ms后解决
    - ![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20230215093056947.png)

# 2 PROFIBUS DP通信被变频器影响，通信中断

## 2.1 现象

- 客户PROFIBUS DP通信，距离通信模块1.5米处有个变频器；变频器不启动时，正常通信；变频器启动后，就会通信中断。
- 模块状态
    - ![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20231222165545064.png)
    - ![](FILES/33902%20General%20fault%20in%20the%20device%20driver/image-20231222165851330.png)

## 2.2 原因与解决方式

- X20IF1061-1模块的终端电阻没有拨好。
- 重新拨上后，此问题解决。
