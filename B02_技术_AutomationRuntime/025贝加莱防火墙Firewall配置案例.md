## 背景知识
- [023贝加莱操作系统支持防火墙功能吗](023贝加莱操作系统支持防火墙功能吗.md)
- [024如何在Automation Studio中配置防火墙](024如何在Automation%20Studio中配置防火墙.md)
## 配置基本规则
- 添加 Firewall rule 时需要注意:
    - 对于同一规则
        - 如果先放行，那么后续再添加的阻挡策略就不会生效；
        - 反之，如果先阻挡，那么后续的放行就不会生效。
    - 如果希望对同一规则下增加例外
        - Apply Action 设置为 If no other rule applies
        - ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133015670.png)
- 防火墙功能在仿真模式下，相关功能会存在异常，因此建议在硬件 PLC 上测试。

## 检查 PLC 上开放端口方式
- 端口扫描工具
    - [https://www.advanced-port-scanner.com/cn/](https://www.advanced-port-scanner.com/cn/)
- 默认情况下开启 ModbusTCP Slave 功能的 PLC 开放的端口
    - ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133754631.png)
## 案例一：只允许指定 IP 访问 PLC
### 配置方式
- 只允许 IP 为 10.86.13.249 的设备访问 
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133115764.png)
### 实现效果
- PC 的 IP 地址为 10.86.13.249 可以访问
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133352266.png)

- PC 的 IP 地址为 10.86.13.248 不可以访问
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133502871.png)

## 案例二: PLC 只开放指定 IP 与指定端口号提供访问
### 配置方式
- 只允许 IP 为 10.86.13.249 的 PC 设备访问
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133936677.png)

### 实现效果
- 端口扫描工具无法扫到其他端口
    - ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611133955037.png)
- 通过 AS 软件能够连接此 PLC
    - ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611134000688.png)
- PLC 的 ModbusTCP Slave 与 Web 服务例如 SDM 均无法访问

## 案例三：关闭指定端口
### 配置方式
- 关闭 PLC 上开启的 111 端口
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611134546402.png)

### 实现效果
- 可见原先默认开放的 111 端口已被关闭
- ![](FILES/025贝加莱防火墙Firewall配置案例/image-20230611134558315.png)

