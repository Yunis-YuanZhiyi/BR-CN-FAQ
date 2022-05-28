# 008如何使用Runtime Utility Center对CF卡中的内容进行备份？
Tags：Runtime Utility Center、CF卡；
A：
Runtime Utility Center是对贝加莱控制器提供各种故障诊断和维修方式的维护工具。安装文件
可以在贝加莱的官网免费下载。
一张CF卡上可包含多个分区，在Windows系统中，CF卡上只有C盘的存储情况是可见的。
Runtime Utility Center可以用来备份和恢复其他分区的数据。操作方式如下：

1.进入Runtime Utility Center，选择Create，modify and execute projects(.pil)
![Img](./FILES/008如何使用Runtime%20Utility%20Center对CF卡中的内容进行备份？.md/img-20220528211946.png)
![Img](./FILES/008如何使用Runtime%20Utility%20Center对CF卡中的内容进行备份？.md/img-20220528211949.png)

2.在Runtime Utility Center的窗口中选择Tools →Back up files from compact-flash，打开文件备份对话框。使用读卡器将CF卡连接至电脑。

3.点击Select disk，选择要备份的CF卡，点击OK。

4.选择要备份的文件，点击Browse指定备份路径，点击Start。等待备份完成后退出并取下CF卡即可。所选文件将会以在选择对话框中相同的结构被储存在目标路径下。

5.通过在Runtime Utility Center的窗口中选择Tools→Restore files to Compact Flash可将选定的文件备份到另外的CF卡中。