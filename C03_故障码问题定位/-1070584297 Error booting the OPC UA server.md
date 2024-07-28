> Tags: #OPC_UA

- [1 -1070584297 Error booting the OPC UA server](#_1--1070584297-error-booting-the-opc-ua-server)
- [2 案例一程序下载后，重启时ASim仿真不能重启，OPCUA端口冲突](#_2-%E6%A1%88%E4%BE%8B%E4%B8%80%E7%A8%8B%E5%BA%8F%E4%B8%8B%E8%BD%BD%E5%90%8E%EF%BC%8C%E9%87%8D%E5%90%AF%E6%97%B6asim%E4%BB%BF%E7%9C%9F%E4%B8%8D%E8%83%BD%E9%87%8D%E5%90%AF%EF%BC%8Copcua%E7%AB%AF%E5%8F%A3%E5%86%B2%E7%AA%81)
- [3 如何在Windows下如何查看端口占用情况](#_3-%E5%A6%82%E4%BD%95%E5%9C%A8windows%E4%B8%8B%E5%A6%82%E4%BD%95%E6%9F%A5%E7%9C%8B%E7%AB%AF%E5%8F%A3%E5%8D%A0%E7%94%A8%E6%83%85%E5%86%B5)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 -1070584297 Error booting the OPC UA server

- AS Help中信息
- 描述
    - OPC UA 服务器启动阶段出现错误。
- 组件的反应
    - 当出现问题时，服务器将退出启动阶段，因此无法使用。
- 原因和解决方案
    - 有关问题原因的其他信息可在 ASCII 数据中找到。通常，由于所需资源不可用，服务器无法启动。
    - 如果 RAM 不足，服务器将无法创建启动所需的对象。
    - 配置的服务器端口已被另一个进程使用。当其他 OPC UA 服务器已从工具包安装并正在运行时，这是在 Windows 中运行 ARsim 环境时常见的问题。这些包含的演示服务器通常使用默认端口号 4840，该端口号不再适用于 ARsim。
        - 要解决此问题，请为其中一个服务器配置不同的端口或退出任何不再使用的 OPC UA 服务器。

# 2 案例一程序下载后，重启时ASim仿真不能重启，OPCUA端口冲突

- 现象一
    - 仿真项目启动时报错，通过查看ARSim的 Console信息，可见如下报错信息
    - `-1070584297 (ERROR, 48, 11799), IpBin=(=0x00000000, *tOpcUaComm", "Error creating server instance (0x80050000)`
    - ![](FILES/-1070584297%20Error%20booting%20the%20OPC%20UA%20server/image-20240728152250789.png)
- 现象二
    - 在线ARSim传程序报错`TransferModuleContent\artransfer.data.tar.gz failed.`
    - ![](FILES/-1070584297%20Error%20booting%20the%20OPC%20UA%20server/image-20240728152446560.png)
- 原因
    - OPC UA默认端口4840被占用。
    - PC电脑上安装了CodeSys软件并启动了服务，4840端口被占用。
- 解决方式
    - 方式一：修改AR项目的OPC UA端口，改为非冲突的端口号
    - 方式二：将CodeSys等软件服务关闭

# 3 如何在Windows下如何查看端口占用情况

- 输入Win + R，输入cmd，调用cmd窗口。
- ![](/B03_技术_诊断/FILES/029SDM网页无法正常访问/image-20230428103735768.png)
- 输入 `netstat -ano` 查看端口占用信息
- ![](/B03_技术_诊断/FILES/029SDM网页无法正常访问/image-20230428103749888.png)
- `netstat -ano|findstr "81"`  查看对应端口被使用情况
- ![](/B03_技术_诊断/FILES/029SDM网页无法正常访问/image-20230428103801003.png)
- `tasklist | findstr “17552”`查看端口对应的任务名
- ![](/B03_技术_诊断/FILES/029SDM网页无法正常访问/image-20230428103809115.png)
- 可以在任务管理器中找到此进程并关闭，或者通过有管理权限的cmd中的命令`taskkill /f /pid 17552` 强行关闭
- ![](/B03_技术_诊断/FILES/029SDM网页无法正常访问/image-20230428103823340.png)

# 4 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-07-28 | LWB<br>YZY | 初次创建 |
