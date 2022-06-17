# 离线模式下安装工控机的runtime到硬盘上

工控机的硬盘拆除不方便，导致无法像制作CF卡一样离线安装runtime系统和应用程序。


1. 使用ghost克隆


使用AS4.5以下版本正常创建项目
烧卡到CF卡，或者u盘
设置工控机BIOS中的启动顺序
        USB disk
        硬盘
使用winPe系统启动工控机
使用ghost工具软件复制CF卡或者u盘到硬盘
再次启动后，工控机即可正常运行runtime

2. 使用AS4.6创建USB安装盘


使用AS4.6创建项目
创建USB安装盘
        Project-->Project Installation-->Create USB Install Drive
设置工控机BIOS中的启动顺序
        USB disk
        硬盘
给硬盘安装系统
        工控机插上u盘，上电后，会自动安装操作系统，并自动按照项目中的设置来配置以太网口地址。
AS联机，下载项目。