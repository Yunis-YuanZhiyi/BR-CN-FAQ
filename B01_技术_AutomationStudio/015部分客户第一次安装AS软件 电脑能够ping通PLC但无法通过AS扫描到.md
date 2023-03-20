# 015部分客户第一次安装AS软件，电脑能够ping通PLC但无法通过AS扫描到
- 原因分析：
    - 无法扫描到PLC是因为Vindows系统的Pcap驱动没有正常工作导致的。
- 解决方案：
    - Win7系统需要重新安装WinPcap驱动，可以上网 https://www.winpcap.org 下载后直接安装；
    - Win10系统需要重新安装PVI,可在贝加菜官网
https://www.br-automation.com/zh/downloads#categories=Software/Automation+NET%2FPVI

安装时需要：
    - 1.确保已有的PVI没有启动(关掉AS即可)，
    - 2.勾选下图中红框标记Install PVI Manager as service
    - ![Img](FILES/015部分客户第一次安装AS软件，电脑能够ping通PLC但无法通过AS扫描到.md/img-20220530144509.png)
