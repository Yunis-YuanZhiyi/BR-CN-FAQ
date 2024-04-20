> Tags: #ACOPOS_P3 #安全链 #SafeDesigner #SafeMOTION

- [1 A05.024-ACOPOS P3 SafeMOTION基本应用](#_1-a05024-acopos-p3-safemotion%E5%9F%BA%E6%9C%AC%E5%BA%94%E7%94%A8)
- [2 硬件配置](#_2-%E7%A1%AC%E4%BB%B6%E9%85%8D%E7%BD%AE)
- [3 软件配置](#_3-%E8%BD%AF%E4%BB%B6%E9%85%8D%E7%BD%AE)
- [4 实际接线图](#_4-%E5%AE%9E%E9%99%85%E6%8E%A5%E7%BA%BF%E5%9B%BE)
- [5 编写程序](#_5-%E7%BC%96%E5%86%99%E7%A8%8B%E5%BA%8F)
- [6 运行监控](#_6-%E8%BF%90%E8%A1%8C%E7%9B%91%E6%8E%A7)
- [7 DEMO程序下载](#_7-demo%E7%A8%8B%E5%BA%8F%E4%B8%8B%E8%BD%BD)
- [8 更新日志](#_8-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 A05.024-ACOPOS P3 SafeMOTION基本应用

- 本文简单介绍X20SL8100+ACOPOS P3 SafeMOTION 的基本使用，安全伺服不同于非安全伺服，必须通过安全逻辑来控制伺服ready和上电使能。
- 本文只是简单介绍，通过一些基本的编程和设置能够让伺服运行。

# 2 硬件配置

- CPU控制器：X20CP1586
- 安全PLC：X20SL8100
- 安全伺服：8EI2X2HWDS0.0A00-1
- 安全电机：8LSA35.DA030S000-3

![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134257966.png)

# 3 软件配置

- AS: 4.7.6.114
- AR: C4.72
- APC10 ARNC0(Motion): 5.9.2
- Safety Release: 1.10

# 4 实际接线图

- 只需要给模块供电，驱动器与电机、编码器之间接线即可。
![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134453686.png)

# 5 编写程序

- <span style="background:#F0A7D8">1___</span>新建工程，添加配置和CPU控制器X20CP1586模块。
- <span style="background:#F0A7D8">2___</span>设置控制器IP地址（略）。
- <span style="background:#F0A7D8">3___</span>添加安全PLC X20SL8100模块，
    - 注意：添加之前需要在AR里先设置好Mapp Safety及Safety Release，否则无法创建安全程序
        - MappSafety 与 Safety Release不能同时选择，此测试仅测试 Safety Release方案。
- <span style="background:#F0A7D8">4___</span>添加安全伺服8E8EI2X2HWDS0.0A00-1，与非安全伺服添加方式一致。按如下配置：
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134623486.png)
    - 初始化参数表按如下设置
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134646955.png)
- <span style="background:#F0A7D8">5___</span>添加单轴样例程序，添加程序，新建BOOL型变量用于控制安全伺服STO功能。
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134715333.png)
    - 进行变量映射
        - gActive：用于激活安全伺服运动功能块
        - gReset：用于安全伺服运动功能块复位
        - gSto：用于STO功能控制
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134757477.png)
- <span style="background:#F0A7D8">6___</span>打开X20SL8100配置，设置安全程序工程名称和版本
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134844201.png)
- <span style="background:#F0A7D8">7___</span>X20SL8100右键选择SafeDESIGNER打开安全PLC编程界面
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134908367.png)
    - 初次打开需要设置工程密码，本程序的工程密码：123456。
    - 关联变量，全局变量是安全PLC与外部交互的变量，需要拖拽到变量表进行关联。
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420134946551.png)
    - 局部变量定义，用于在安全PLC内使用，不与外面交互。
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135016911.png)
    - 安全轴基本配置，功能介绍详见SF_oS_MOTION_Basic_BR功能块介绍
        - 1）安全PLC上电时，功能块自动执行一次复位，不需要程序手动复位
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135043137.png)
        - 2）选择使用编码器，否则报警
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135106385.png)
        - 3）设置编码器监控及偏差报警
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135123781.png)
    - 添加库文件
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135145426.png)
    - 编程
        - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135205540.png)
- <span style="background:#F0A7D8">8___</span>添加VC4画面
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135231974.png)
- <span style="background:#F0A7D8">9___</span>下载程序，安全PLC需要单独下载，下载后上电需要确认操作
    - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135303092.png)

# 6 运行监控

 - AS项目监控
     - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135329247.png)
 - SafeDESGINER软件监控
     - ![](FILES/024ACOPOS%20P3%20SafeMOTION基本应用/image-20240420135340444.png)

# 7 DEMO程序下载

- [贝加莱社区-下载中心-前往下载 ](https://br-community.com/downloadDis/88)

# 8 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2021-06-16 | LWB | 初次创建 |
