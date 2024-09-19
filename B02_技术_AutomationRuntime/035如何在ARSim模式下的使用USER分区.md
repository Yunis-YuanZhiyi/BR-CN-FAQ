> Tags: #文件 #文件系统

- [1 B02.035.如何在ARSim模式下的使用USER分区](#_1-b02035%E5%A6%82%E4%BD%95%E5%9C%A8arsim%E6%A8%A1%E5%BC%8F%E4%B8%8B%E7%9A%84%E4%BD%BF%E7%94%A8user%E5%88%86%E5%8C%BA)
- [2 电脑创建F盘](#_2-%E7%94%B5%E8%84%91%E5%88%9B%E5%BB%BAf%E7%9B%98)
- [3 更新日志](#_3-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B02.035.如何在ARSim模式下的使用USER分区

- AS4.10之后的版本，Module system on target只能选择SAFE，这导致了如果需要读写外部文件，文件只能存放在USER空间，即PLC的CF卡中的F盘中
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819110430671.png)
- 我们习惯在File devices中将Path指定为 `F:\` ，但当开启仿真模式，需要电脑本地也需要一个F盘。
- 此文档介绍如何手动划分笔记本的电脑的硬盘区域，指定一个专门的F盘用于测试。

# 2 电脑创建F盘

- <span style="background:#A0CCF6">1___</span>打开文件管理器，右键PC，选择Manage(管理)，找到 Disk Management（磁盘管理）
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819111345211.png)
    - 磁盘管理也可以从运行窗口启动。按 Windows+R，在框中键入“diskmgmt.msc”，然后单击“确定”。
- <span style="background:#A0CCF6">2___</span>点击C盘，右键 → 选择 Shrink Volume (压缩卷 )，在弹出框中输入需要F盘容量（单位为MB）并选择收缩，以下图为例，分配了512MB的硬盘空间。
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819111700219.png)
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819112645990.png)
- <span style="background:#A0CCF6">3___</span>选中刚刚分配好的分区卷，右键 → New Simple Volume，→ 选择需要分配给的盘符为 F → 命名此卷并格式化（需注意要选择FAT32）
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819112326889.png)
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819124701622.png)
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819125053950.png)
- <span style="background:#A0CCF6">4___</span>格式化完成，将文件放置在指定路径即可
    - ![undefined](FILES/035如何在ARSim模式下的使用USER分区/image-20240819125125858.png)

# 3 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-08-19 | YZY | 初次创建 |
