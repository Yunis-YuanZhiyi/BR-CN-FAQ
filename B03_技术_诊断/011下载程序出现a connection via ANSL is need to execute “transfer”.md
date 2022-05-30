# 011下载程序出现a connection via ANSL is need to execute “transfer”
- 一般通过关闭AS软件重开即可解决
- 另一种解决方式：
    - 1、打开online→settings，选择标签页“Serial”，用串口连接一下PLC（不需要真的与PLC建立串口的物理连接，只需要在AS中操作一下即可）。如下图：
    - ![Img](./FILES/011下载程序出现a%20connection%20via%20ANSL%20is%20need%20to%20execute%20“transfer”.md/img-20220530143901.png)
    - 2、由于没有真的与PLC建立串口的物理连接，所以下方状态栏会显示“OFFLINE
    - 3、再次切换回标签页“Ethernet”，使用IP地址连接实际PLC即可。