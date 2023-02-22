详情可下载贝加莱Hypervisor使用助手

## 下载地址
[贝加莱知识库 (huashengyun.online)](https://brtechs.huashengyun.online/index.php?mod=bjl&do=file&gid=19#group&do=file&gid=19&fid=2855)
> 登录后再次点击链接即可自动

![](FILES/017Hypervisor安装与使用问题/image-20230221144345725.png)

## CHM文件显示
![](FILES/017Hypervisor安装与使用问题/image-20230221143845910.png)

## 常见问题列表
- Q1:Hypervisor安装停留在界面
- Q2:Hyervisor装完之后进入windows就崩溃，删除后能正常启动
- Q3:Hypervisor装完后一直重启，最后进入花屏
- Q4:Hypervisor安装完后停留在界面
- Q5:Hypervisor安装完成后直接进入Win10没有重启
- Q6:Linux下装好后启动，停留在黑屏。
- Q7:对PPC2100硬件，基于AR4.8的U盘安装Hypervisor，在线更新后，CPU原有的3核变为1核。
- Q8:APC2200，装完hypervisor后，windows（非官方镜像）在第三次断电后出现需要恢复，无法正常启动
- Q9:APC3100，装完hypervisor及驱动后，windows网口无法使用，显示驱动损坏
- Q10:当已正确安装Hypervisor，系统也已提示安装Hypervisor正确安装，在重启后发现卡在此步骤不动，应该如何处理。
- Q11:通过USB installation stick进行安装Hypervisor，在Install之后，没有正常安装，提示Error:
- Q12:工控机Windows安装界面卡在Recovery Solution，点击Start无法进入下一步
- Q13:客户在已安装Hypervisor的工控机上下载程序时报错
- Q14:重新启动后，安装冻结，无法继续。 – ARemb 在RUN的状态
- Q15: 重新启动后安装冻结，无法继续 - ARemb在SERVICE模式
- Q16: Windows循环重启，并带有错误码: INACCESIBLE BOOT DEVICE
- Q17:安装GPOS上的驱动时报错
- Q18:在UEFI APC上安装Hypervisor的常见问题
- Q19:为Hypervisor分配太多的内存
- Q20:使用APC910 TS77-04安装Hypervisor，启动后显示器显示花屏
- Q21:Hypervisor的驱动安装了，但内部的虚拟网口无法被找到
- Q22:安装Hypervisor，提示Hypervisor无法安装在UEFI操作系统上
- Q23:AS4.7安装Hypervisor在Win10操作系统后，操作系统一直进入蓝屏状态，重启后仍然会进入蓝屏
- Q24:安装Hypervisor后，屏幕花屏
- Q25:使用了性能较差的CF卡作为USB Installation Stick，导致安装异常
- Q26:PPC2200之类的设备，使用Debian系统，在镜像到不同屏幕上，触摸功能失效
- Q27:安装好Hypervisor后的Windows系统如何再次分区？
- Q28:安装Hypervisor后提示安装成功，但实际Hypervisor没有启动，ETH口无法连上
- Q29:在APC910-QM77上安装Hypervisor报错提示Virtualization is disabled by the firmware
- Q30:5ACPCE.ETH4-00卡能否支持Hypervisor？
- Q31:在操作系统为Debian 10上的APC910 TS17-04设备上安装Hypervisor，提示configuration not loaded by bootloader
- Q32:安装Hypervisor驱动时，提示A backup of the original boot loader already exists.
- Q33:原先安装正常使用的Hypervisor，卸载安装其他版本的Hypervisor，出现 The original boot loader could not be backuped
- Q34:Hypervisor在USB更新程序后无法启动显示License is not valid
- Q35:给一台全新的硬件安装Hypervisor提示Uninstall

## 常见使用案例问题
1.我无法从ArEmb/Windows访问SSD。可能是什么问题？
2.带有管理程序和Linux Debian 9的系统，PPC无法启动Linux 系统
3.如何避免外部网络线缆短接并使用VNC Viewer？
4.我们正面临着Visual Basic应用程序--在Windows（APC-GPOS）和ArEmb之间通过内部桥接进行PVI通信的问题。
5.需要从mapp View，关闭Linux Debien 9系统。
6.有可能只关闭 Linux吗？
7.在Hypervisor中是否有任何设置可用于Windows系统和ArEmb 系统之间的时间同步？
8.在将OrangeBox升级到Nestle OrangeBox时，产生了数据库错误。有什么可能的解决方案？
9.我们正试图通过VCWT在PPC2100的Hypervisor+Windows 10中操作VC4，但我们无法做到这一点。 有什么可能的解决方法？
10.我们正面临着Hypervisor和Zenon SCADA的PVI通信问题
11.我们在windows上用Hypervisor创建的分区数量有什么限制吗？
12.我们正在使用带有ArWin的APC3100和（5E9030.29）RFID转发器。我们想在该RFID上读取和写入数据。是否有可能用ArWin来做这件事？
13.Hypervisor是否需要PVI许可证？
14.如果ArEmb处于服务模式，在VNC浏览器/Linux中没有关于服务模式的信息。有什么方法可以获得ArEmb的状态（不需要额外的编程）并在Linux Debian中显示出来？
15.我们正在使用带有Hypervisor的PPC2200，我们能够在ArEmb中记录数据并创建MpReport，但不能通过 CIFS将这些文件保存到WindowC盘。
16.我们正在使用APC3100，但现在想用windows系统安装Hypervisor，但根据帮助，Hypervisor环境必须被启用，而它被禁用了（它被锁定，不能编辑）
17.在没有hypervisor许可证的情况下，Hypervisor工作正常，是否真的需要在机器上使用Hypervisor许可证？
18.Hypervisor下两个系统(GPOS与ARemb)之间实现通讯交互