> #Hypervisor #问题处理

- [1 B02.026-Hypervisor常见问题一览](#_1-b02026-hypervisor%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E4%B8%80%E8%A7%88)
- [2 Hypervisor安装启动中出现 /OS/1 I/O access blocked. 影响安装吗？](#_2-hypervisor%E5%AE%89%E8%A3%85%E5%90%AF%E5%8A%A8%E4%B8%AD%E5%87%BA%E7%8E%B0-os1-io-access-blocked-%E5%BD%B1%E5%93%8D%E5%AE%89%E8%A3%85%E5%90%97%EF%BC%9F)
- [3 Hypervisor安装停留在界面](#_3-hypervisor%E5%AE%89%E8%A3%85%E5%81%9C%E7%95%99%E5%9C%A8%E7%95%8C%E9%9D%A2)
- [4 Hyervisor装完之后进入windows就崩溃，删除后能正常启动](#_4-hyervisor%E8%A3%85%E5%AE%8C%E4%B9%8B%E5%90%8E%E8%BF%9B%E5%85%A5windows%E5%B0%B1%E5%B4%A9%E6%BA%83%EF%BC%8C%E5%88%A0%E9%99%A4%E5%90%8E%E8%83%BD%E6%AD%A3%E5%B8%B8%E5%90%AF%E5%8A%A8)
- [5 Hypervisor装完后一直重启，最后进入花屏](#_5-hypervisor%E8%A3%85%E5%AE%8C%E5%90%8E%E4%B8%80%E7%9B%B4%E9%87%8D%E5%90%AF%EF%BC%8C%E6%9C%80%E5%90%8E%E8%BF%9B%E5%85%A5%E8%8A%B1%E5%B1%8F)
- [6 Hypervisor安装完后停留在界面](#_6-hypervisor%E5%AE%89%E8%A3%85%E5%AE%8C%E5%90%8E%E5%81%9C%E7%95%99%E5%9C%A8%E7%95%8C%E9%9D%A2)
- [7 Hypervisor安装完成后直接进入Win10没有重启。](#_7-hypervisor%E5%AE%89%E8%A3%85%E5%AE%8C%E6%88%90%E5%90%8E%E7%9B%B4%E6%8E%A5%E8%BF%9B%E5%85%A5win10%E6%B2%A1%E6%9C%89%E9%87%8D%E5%90%AF)
- [8 Linux下装好后启动，停留在黑屏。](#_8-linux%E4%B8%8B%E8%A3%85%E5%A5%BD%E5%90%8E%E5%90%AF%E5%8A%A8%EF%BC%8C%E5%81%9C%E7%95%99%E5%9C%A8%E9%BB%91%E5%B1%8F)
- [9 对PPC2100硬件，基于AR4.8的U盘安装Hypervisor，在线更新后，CPU原有的3核变为1核。](#_9-%E5%AF%B9ppc2100%E7%A1%AC%E4%BB%B6%EF%BC%8C%E5%9F%BA%E4%BA%8Ear48%E7%9A%84u%E7%9B%98%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E5%9C%A8%E7%BA%BF%E6%9B%B4%E6%96%B0%E5%90%8E%EF%BC%8Ccpu%E5%8E%9F%E6%9C%89%E7%9A%843%E6%A0%B8%E5%8F%98%E4%B8%BA1%E6%A0%B8)
- [10 APC2200，装完hypervisor后，windows（非官方镜像）在第三次断电后出现需要恢复，无法正常启动](#_10-apc2200%EF%BC%8C%E8%A3%85%E5%AE%8Chypervisor%E5%90%8E%EF%BC%8Cwindows%EF%BC%88%E9%9D%9E%E5%AE%98%E6%96%B9%E9%95%9C%E5%83%8F%EF%BC%89%E5%9C%A8%E7%AC%AC%E4%B8%89%E6%AC%A1%E6%96%AD%E7%94%B5%E5%90%8E%E5%87%BA%E7%8E%B0%E9%9C%80%E8%A6%81%E6%81%A2%E5%A4%8D%EF%BC%8C%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%90%AF%E5%8A%A8)
- [11 APC3100，装完hypervisor及驱动后，windows网口无法使用，显示驱动损坏](#_11-apc3100%EF%BC%8C%E8%A3%85%E5%AE%8Chypervisor%E5%8F%8A%E9%A9%B1%E5%8A%A8%E5%90%8E%EF%BC%8Cwindows%E7%BD%91%E5%8F%A3%E6%97%A0%E6%B3%95%E4%BD%BF%E7%94%A8%EF%BC%8C%E6%98%BE%E7%A4%BA%E9%A9%B1%E5%8A%A8%E6%8D%9F%E5%9D%8F)
- [12 当已正确安装Hypervisor，系统也已提示安装Hypervisor正确安装，在重启后发现卡在此步骤不动，应该如何处理。](#_12-%E5%BD%93%E5%B7%B2%E6%AD%A3%E7%A1%AE%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E7%B3%BB%E7%BB%9F%E4%B9%9F%E5%B7%B2%E6%8F%90%E7%A4%BA%E5%AE%89%E8%A3%85hypervisor%E6%AD%A3%E7%A1%AE%E5%AE%89%E8%A3%85%EF%BC%8C%E5%9C%A8%E9%87%8D%E5%90%AF%E5%90%8E%E5%8F%91%E7%8E%B0%E5%8D%A1%E5%9C%A8%E6%AD%A4%E6%AD%A5%E9%AA%A4%E4%B8%8D%E5%8A%A8%EF%BC%8C%E5%BA%94%E8%AF%A5%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86)
- [13 通过USB installation stick进行安装Hypervisor，在Install之后，没有正常安装，提示Error:](#_13-%E9%80%9A%E8%BF%87usb-installation-stick%E8%BF%9B%E8%A1%8C%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E5%9C%A8install%E4%B9%8B%E5%90%8E%EF%BC%8C%E6%B2%A1%E6%9C%89%E6%AD%A3%E5%B8%B8%E5%AE%89%E8%A3%85%EF%BC%8C%E6%8F%90%E7%A4%BAerror)
- [14 工控机Windows安装界面卡在Recovery Solution，点击Start无法进入下一步](#_14-%E5%B7%A5%E6%8E%A7%E6%9C%BAwindows%E5%AE%89%E8%A3%85%E7%95%8C%E9%9D%A2%E5%8D%A1%E5%9C%A8recovery-solution%EF%BC%8C%E7%82%B9%E5%87%BBstart%E6%97%A0%E6%B3%95%E8%BF%9B%E5%85%A5%E4%B8%8B%E4%B8%80%E6%AD%A5)
- [15 客户在已安装Hypervisor的工控机上下载程序时报错](#_15-%E5%AE%A2%E6%88%B7%E5%9C%A8%E5%B7%B2%E5%AE%89%E8%A3%85hypervisor%E7%9A%84%E5%B7%A5%E6%8E%A7%E6%9C%BA%E4%B8%8A%E4%B8%8B%E8%BD%BD%E7%A8%8B%E5%BA%8F%E6%97%B6%E6%8A%A5%E9%94%99)
- [16 重新启动后，安装冻结，无法继续 – ARemb 在RUN的状态](#_16-%E9%87%8D%E6%96%B0%E5%90%AF%E5%8A%A8%E5%90%8E%EF%BC%8C%E5%AE%89%E8%A3%85%E5%86%BB%E7%BB%93%EF%BC%8C%E6%97%A0%E6%B3%95%E7%BB%A7%E7%BB%AD--aremb-%E5%9C%A8run%E7%9A%84%E7%8A%B6%E6%80%81)
- [17 重新启动后安装冻结，无法继续 - ARemb在SERVICE模式](#_17-%E9%87%8D%E6%96%B0%E5%90%AF%E5%8A%A8%E5%90%8E%E5%AE%89%E8%A3%85%E5%86%BB%E7%BB%93%EF%BC%8C%E6%97%A0%E6%B3%95%E7%BB%A7%E7%BB%AD---aremb%E5%9C%A8service%E6%A8%A1%E5%BC%8F)
- [18 Windows循环重启，并带有错误码: INACCESIBLE BOOT DEVICE](#_18-windows%E5%BE%AA%E7%8E%AF%E9%87%8D%E5%90%AF%EF%BC%8C%E5%B9%B6%E5%B8%A6%E6%9C%89%E9%94%99%E8%AF%AF%E7%A0%81-inaccesible-boot-device)
- [19 安装GPOS上的驱动时报错](#_19-%E5%AE%89%E8%A3%85gpos%E4%B8%8A%E7%9A%84%E9%A9%B1%E5%8A%A8%E6%97%B6%E6%8A%A5%E9%94%99)
- [20 在UEFI APC上安装Hypervisor的常见问题](#_20-%E5%9C%A8uefi-apc%E4%B8%8A%E5%AE%89%E8%A3%85hypervisor%E7%9A%84%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
- [21 为Hypervisor分配太多的内存](#_21-%E4%B8%BAhypervisor%E5%88%86%E9%85%8D%E5%A4%AA%E5%A4%9A%E7%9A%84%E5%86%85%E5%AD%98)
- [22 使用APC910 TS77-04安装Hypervisor，启动后显示器显示花屏](#_22-%E4%BD%BF%E7%94%A8apc910-ts77-04%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E5%90%AF%E5%8A%A8%E5%90%8E%E6%98%BE%E7%A4%BA%E5%99%A8%E6%98%BE%E7%A4%BA%E8%8A%B1%E5%B1%8F)
- [23 Hypervisor的驱动安装了，但内部的虚拟网口无法被找到](#_23-hypervisor%E7%9A%84%E9%A9%B1%E5%8A%A8%E5%AE%89%E8%A3%85%E4%BA%86%EF%BC%8C%E4%BD%86%E5%86%85%E9%83%A8%E7%9A%84%E8%99%9A%E6%8B%9F%E7%BD%91%E5%8F%A3%E6%97%A0%E6%B3%95%E8%A2%AB%E6%89%BE%E5%88%B0)
- [24 安装Hypervisor，提示Hypervisor无法安装在UEFI操作系统上](#_24-%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E6%8F%90%E7%A4%BAhypervisor%E6%97%A0%E6%B3%95%E5%AE%89%E8%A3%85%E5%9C%A8uefi%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E4%B8%8A)
- [25 AS4.7安装Hypervisor在Win10操作系统后，操作系统一直进入蓝屏状态，重启后仍然会进入蓝屏](#_25-as47%E5%AE%89%E8%A3%85hypervisor%E5%9C%A8win10%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E5%90%8E%EF%BC%8C%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E4%B8%80%E7%9B%B4%E8%BF%9B%E5%85%A5%E8%93%9D%E5%B1%8F%E7%8A%B6%E6%80%81%EF%BC%8C%E9%87%8D%E5%90%AF%E5%90%8E%E4%BB%8D%E7%84%B6%E4%BC%9A%E8%BF%9B%E5%85%A5%E8%93%9D%E5%B1%8F)
- [26 安装Hypervisor后，屏幕花屏](#_26-%E5%AE%89%E8%A3%85hypervisor%E5%90%8E%EF%BC%8C%E5%B1%8F%E5%B9%95%E8%8A%B1%E5%B1%8F)
- [27 使用了性能较差的CF卡作为USB Installation Stick，导致安装异常](#_27-%E4%BD%BF%E7%94%A8%E4%BA%86%E6%80%A7%E8%83%BD%E8%BE%83%E5%B7%AE%E7%9A%84cf%E5%8D%A1%E4%BD%9C%E4%B8%BAusb-installation-stick%EF%BC%8C%E5%AF%BC%E8%87%B4%E5%AE%89%E8%A3%85%E5%BC%82%E5%B8%B8)
- [28 PPC2200之类的设备，使用Debian系统，在镜像到不同屏幕上，触摸功能失效](#_28-ppc2200%E4%B9%8B%E7%B1%BB%E7%9A%84%E8%AE%BE%E5%A4%87%EF%BC%8C%E4%BD%BF%E7%94%A8debian%E7%B3%BB%E7%BB%9F%EF%BC%8C%E5%9C%A8%E9%95%9C%E5%83%8F%E5%88%B0%E4%B8%8D%E5%90%8C%E5%B1%8F%E5%B9%95%E4%B8%8A%EF%BC%8C%E8%A7%A6%E6%91%B8%E5%8A%9F%E8%83%BD%E5%A4%B1%E6%95%88)
- [29 安装好Hypervisor后的Windows系统如何再次分区？](#_29-%E5%AE%89%E8%A3%85%E5%A5%BDhypervisor%E5%90%8E%E7%9A%84windows%E7%B3%BB%E7%BB%9F%E5%A6%82%E4%BD%95%E5%86%8D%E6%AC%A1%E5%88%86%E5%8C%BA%EF%BC%9F)
- [30 安装Hypervisor后提示安装成功，但实际Hypervisor没有启动，ETH口无法连上。](#_30-%E5%AE%89%E8%A3%85hypervisor%E5%90%8E%E6%8F%90%E7%A4%BA%E5%AE%89%E8%A3%85%E6%88%90%E5%8A%9F%EF%BC%8C%E4%BD%86%E5%AE%9E%E9%99%85hypervisor%E6%B2%A1%E6%9C%89%E5%90%AF%E5%8A%A8%EF%BC%8Ceth%E5%8F%A3%E6%97%A0%E6%B3%95%E8%BF%9E%E4%B8%8A)
- [31 在APC910-QM77上安装Hypervisor报错提示Virtualization is disabled by the firmware](#_31-%E5%9C%A8apc910-qm77%E4%B8%8A%E5%AE%89%E8%A3%85hypervisor%E6%8A%A5%E9%94%99%E6%8F%90%E7%A4%BAvirtualization-is-disabled-by-the-firmware)
- [32 5ACPCE.ETH4-00卡能否支持Hypervisor？](#_32-5acpceeth4-00%E5%8D%A1%E8%83%BD%E5%90%A6%E6%94%AF%E6%8C%81hypervisor%EF%BC%9F)
- [33 在操作系统为Debian 10上的APC910 TS17-04设备上安装Hypervisor，提示如下报错](#_33-%E5%9C%A8%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E4%B8%BAdebian-10%E4%B8%8A%E7%9A%84apc910-ts17-04%E8%AE%BE%E5%A4%87%E4%B8%8A%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E6%8F%90%E7%A4%BA%E5%A6%82%E4%B8%8B%E6%8A%A5%E9%94%99)
- [34 安装Hypervisor驱动时，提示A backup of the original boot loader already exists.](#_34-%E5%AE%89%E8%A3%85hypervisor%E9%A9%B1%E5%8A%A8%E6%97%B6%EF%BC%8C%E6%8F%90%E7%A4%BAa-backup-of-the-original-boot-loader-already-exists)
- [35 原先安装正常使用的Hypervisor，卸载安装其他版本的Hypervisor，出现 The original boot loader could not be backuped](#_35-%E5%8E%9F%E5%85%88%E5%AE%89%E8%A3%85%E6%AD%A3%E5%B8%B8%E4%BD%BF%E7%94%A8%E7%9A%84hypervisor%EF%BC%8C%E5%8D%B8%E8%BD%BD%E5%AE%89%E8%A3%85%E5%85%B6%E4%BB%96%E7%89%88%E6%9C%AC%E7%9A%84hypervisor%EF%BC%8C%E5%87%BA%E7%8E%B0-the-original-boot-loader-could-not-be-backuped)
- [36 Hypervisor在USB更新程序后无法启动显示License is not valid](#_36-hypervisor%E5%9C%A8usb%E6%9B%B4%E6%96%B0%E7%A8%8B%E5%BA%8F%E5%90%8E%E6%97%A0%E6%B3%95%E5%90%AF%E5%8A%A8%E6%98%BE%E7%A4%BAlicense-is-not-valid)
- [37 给一台全新的硬件安装Hypervisor提示Uninstall](#_37-%E7%BB%99%E4%B8%80%E5%8F%B0%E5%85%A8%E6%96%B0%E7%9A%84%E7%A1%AC%E4%BB%B6%E5%AE%89%E8%A3%85hypervisor%E6%8F%90%E7%A4%BAuninstall)
- [38 安装过程中 Hypervisor 重启几次后，卡在/OS/1 Booting runtime 0 状态](#_38-%E5%AE%89%E8%A3%85%E8%BF%87%E7%A8%8B%E4%B8%AD-hypervisor-%E9%87%8D%E5%90%AF%E5%87%A0%E6%AC%A1%E5%90%8E%EF%BC%8C%E5%8D%A1%E5%9C%A8os1-booting-runtime-0-%E7%8A%B6%E6%80%81)
- [39 U盘安装Hypervisor，在系统选择从U盘启动时提示BOOTMGR is missing](#_39-u%E7%9B%98%E5%AE%89%E8%A3%85hypervisor%EF%BC%8C%E5%9C%A8%E7%B3%BB%E7%BB%9F%E9%80%89%E6%8B%A9%E4%BB%8Eu%E7%9B%98%E5%90%AF%E5%8A%A8%E6%97%B6%E6%8F%90%E7%A4%BAbootmgr-is-missing)
- [40 安装Hypervisor提示Hypervisor boot failed.](#_40-%E5%AE%89%E8%A3%85hypervisor%E6%8F%90%E7%A4%BAhypervisor-boot-failed)
- [41 安装卡在30%，出现欢迎访问Buildroot的信息](#_41-%E5%AE%89%E8%A3%85%E5%8D%A1%E5%9C%A830%25%EF%BC%8C%E5%87%BA%E7%8E%B0%E6%AC%A2%E8%BF%8E%E8%AE%BF%E9%97%AEbuildroot%E7%9A%84%E4%BF%A1%E6%81%AF)
- [42 在APC3100上安装Hypervisor提示You cannot install B&R Hypervisor on a UEFI system when you have booted the USB install stick with legacy.](#_42-%E5%9C%A8apc3100%E4%B8%8A%E5%AE%89%E8%A3%85hypervisor%E6%8F%90%E7%A4%BAyou-cannot-install-br-hypervisor-on-a-uefi-system-when-you-have-booted-the-usb-install-stick-with-legacy)
- [43 使用AS4.10，Hypervisor安装提示 No EFI system partition (ESP) found](#_43-%E4%BD%BF%E7%94%A8as410%EF%BC%8Chypervisor%E5%AE%89%E8%A3%85%E6%8F%90%E7%A4%BA-no-efi-system-partition-esp-found)
- [44 更新日志](#_44-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B02.026-Hypervisor常见问题一览

# 2 Hypervisor安装启动中出现 /OS/1 I/O access blocked. 影响安装吗？

- A0:
- 在安装过程中，系统试图检测一个串行接口。如果所使用的硬件上没有这个接口，就会输出以下警告。
- ![](FILES/026Hypervisor常见问题一览/a349e0f6fc0f003b05fcc48bd531a9b3.png)
- 这些警告并不影响安装程序。

# 3 Hypervisor安装停留在界面

- A1: USB安装盘插在了windows口上
- ![](FILES/026Hypervisor常见问题一览/3010831b35b19514b2e0feac8505c10f.png)

# 4 Hyervisor装完之后进入windows就崩溃，删除后能正常启动

- A2:重装ADI驱动

# 5 Hypervisor装完后一直重启，最后进入花屏

- A3:更新AS版本补丁包

# 6 Hypervisor安装完后停留在界面

- A4:CPU型号选错
- ![](FILES/026Hypervisor常见问题一览/b66b058c581401a467b1891500b02353.png)

# 7 Hypervisor安装完成后直接进入Win10没有重启。

- A5:BIOS中BOOT启动项要选择B&R Hypervisor（最近采购的工控机才有的选项）

# 8 Linux下装好后启动，停留在黑屏。

- A6:一开始使用的AR版本是B4.82，换成B4.62，成功
- ![](FILES/026Hypervisor常见问题一览/e3042b41dda45f379daaeb2403583fd8.png)
- ![](FILES/026Hypervisor常见问题一览/195d7f66317e34ba1a382e4aa2bb69b1.png)

# 9 对PPC2100硬件，基于AR4.8的U盘安装Hypervisor，在线更新后，CPU原有的3核变为1核。

- A7:换用AR4.7及以下，通过U盘安装Hypervisor。之后通过AS4.8进行在线更新，则没有问题

# 10 APC2200，装完hypervisor后，windows（非官方镜像）在第三次断电后出现需要恢复，无法正常启动

- A8:
- **操作步骤**
    - 在 Win 10 系统下按 Win+R 按键，启动 【命令行 (管理员模式)】。注意：一定要是管理员模式。
    - 依次输入如下命令（注意空格和符号）：

```
bcdedit /set bootstatuspolicy ignoreallfailures
bcdedit /set recoveryenabled No
bcdedit /set {current} bootstatuspolicy ignoreallfailures
bcdedit /set {current} recoveryenabled No
bcdedit /set {globalsettings} advancedoptions false
```

- 正常重启计算机一次。然后就可以测试效果了，这时再出现三次不正常启动也就不会出现恢复选项了。
- ![](FILES/026Hypervisor常见问题一览/3063f8b2a46e3f3782738e15b4467153.png)

# 11 APC3100，装完hypervisor及驱动后，windows网口无法使用，显示驱动损坏

- A9:
- 操作步骤：
    - 原AS版本4.10，AR版本B4.91。将AR版本升级至D4.91。
    - 在Windows管理器内卸载BR Hypervisor。
    - 将升级AR后的程序下载至工控机内。
    - 重新安装Windows的BR Hypervisor。

# 12 当已正确安装Hypervisor，系统也已提示安装Hypervisor正确安装，在重启后发现卡在此步骤不动，应该如何处理。

- ![](FILES/026Hypervisor常见问题一览/238de540c0243f2150917d239d01c59f.png)
- A10:
    - 1.确认BIOS版本、Firmware版本、在Linux系统上的驱动是否正确安装了。可能BIOS与Firmware使用了旧的版本或者不正确不匹配的版本。（64Bit、32Bit，不同的GPOS对应的固件版本以及BIOS）
    - 2.更新顺序必须为更新BIOS，再更新Firmware，再更新GPOS上安装的驱动。否则无效。
    - **尝试看看ARemb是否已经起来了，使用Automation Studio软件连接上，更新ARemb程序看是否能够解决。**

# 13 通过USB installation stick进行安装Hypervisor，在Install之后，没有正常安装，提示Error:

- ![](FILES/026Hypervisor常见问题一览/75be8d8dc8d040d3f470cbe3b81fda02.png)
- A11:
- 此问题即是分区资源分配的不合理导致。需检查并确认：
    - 硬盘最后的区域属于 unallocated 状态且不小于1GB，
    - 划分出来的区域不是Windows下的扩展分区
    - 通过DiskGenius软件检查并确认了系统的分区情况合理
- 当系统进入Welcome to Buildroot这类Makefiles和patches的命令集，则可按Ctrl+Alt+Delete让系统自动重启。

# 14 工控机Windows安装界面卡在Recovery Solution，点击Start无法进入下一步

- ![](FILES/026Hypervisor常见问题一览/6bddef068878e5102be10b4abbeb3c94.png)
- **问题原因**：
    - 工控机无法识别到硬盘（CFast）
- **A12**：
    - 将Cfast卡插拔下，能在BIOS中识别到就可以进入下一步

# 15 客户在已安装Hypervisor的工控机上下载程序时报错

- （客户程序中使用SAFE分区并分配了500MB User空间，安装的Hypervisor镜像中也使用了SAFE分区但是未分配User空间）
- ![](FILES/026Hypervisor常见问题一览/9fed5385e5476c6f61dd9d98f87e1379.png)
- A13: 使用SAFE分区并分配500MB User空间的Hypervisor镜像重新安装后客户可以正常下载程序

# 16 重新启动后，安装冻结，无法继续 – ARemb 在RUN的状态

- **典型的终端信息情况**:
    - 黑屏终端提示，末尾信息为 /OS/1 Booting runtime 0 information
    - ![](FILES/026Hypervisor常见问题一览/130d3f692804e0440280ff7d03f64ad4.png)
    - 有可能通过AS中分配给ARemb的ETH端口连接到ARemd，并且ARemb处于RUN模式。
    - ![](FILES/026Hypervisor常见问题一览/7ffc44c9509d6dec53d17c83e7b89630.png)
    - AS → Online → Compare → Software中的差异如下
    - ![](FILES/026Hypervisor常见问题一览/338e36628dd9f4d1aa874800281c1bfb.png)
    - GPOS不启动
    - 无法从U盘中继续安装
    - 当你直接通过ETH端口从AS下载应用程序到ARemb时，GPOS将启动。
- **A14**:
    - U盘被插在APC上错误的USB端口上。有必要将U盘插入APC上的USB端口，该端口在AS中分配给ARemb。
    - ![](FILES/026Hypervisor常见问题一览/9b68d130aa6bb9f14402de03349410da.png)

# 17 重新启动后安装冻结，无法继续 - ARemb在SERVICE模式

- **典型的终端信息情况**:
    - 黑屏终端提示，末尾信息为 /OS/1 Booting runtime 0 information
    - ![](FILES/026Hypervisor常见问题一览/a313481f25956f5195329d4402697700.png)
    - 有可能通过AS中分配给ARemb的ETH端口连接到ARemd，并且ARemb处于SERV模式。
        - ![](FILES/026Hypervisor常见问题一览/15086d246a992cd49622e7399476f811.png)
    - AS → Online → Compare → Software中显示的差异如下
        - ![](FILES/026Hypervisor常见问题一览/fba72c173b57249314c48bf229365e8c.png)
    - GPOS不启动
    - 从U盘中无法继续安装
- **A15**:
    - 当你打开Online → Compare → Hardware，检查AS中使用的HW和目标上真正使用的HW，你会发现有差别。
    - ![](FILES/026Hypervisor常见问题一览/82b120e18f16e5ef93f55d6506455df3.png)
    - 如果你将HW配置改为正确的配置，一切都应该运行。

# 18 Windows循环重启，并带有错误码: INACCESIBLE BOOT DEVICE

- **现象**
    - Windows循环重启
    - 蓝色窗口并带有如下Stop Code: INACESSIBLE BOOT DEVICE
    - ![](FILES/026Hypervisor常见问题一览/0a6df0c239dc75b5a07e8ea1ca4970a8.png)
    - ARemb 在 RUN 状态
        - ![](FILES/026Hypervisor常见问题一览/8141f2299af5d197847c05374b0b89cd.png)
- **A16**:
    - 原因是IDE ATA/ATAPI控制器没有设置为标准AHCI 1.0。
    - ![](FILES/026Hypervisor常见问题一览/ea054570f8b5ca7436fea16a04fadd1f.png)
    - 这也意味着在这种情况下，GPOS驱动程序没有安装到Windows中。

# 19 安装GPOS上的驱动时报错

- **现象**
    - 当你从AS中为管理程序生成安装USB时，也有一个GPOS的驱动程序，它创建了虚拟的ETH端口，以便于从ARemb到GPOS的通信。这个驱动程序在USB的BRHypervisor/GPOSDrivers/Windows中。
    - 在APC上安装Hypervisor之前，有必要在Windows上安装这个驱动程序。
    - 安装时会返回错误，提示必须先卸载AHCI驱动程序。
    - ![](FILES/026Hypervisor常见问题一览/2dcf406ff6c307fc66f77cd3d30dbcea.png)
- **A17**：
    - 检查IDE ATA/ATAPI控制器
    - 这取决于APC的类型，但有些APC不使用de-fail的标准AHCI 1.0串行控制器，而是使用例如英特尔的。为了正确安装Hypervisor，有必要改变这个控制器。
    - 具体操作方式请参考此章节。
    - ![](FILES/026Hypervisor常见问题一览/02172ff1f43fd553962517991985e4e0.png)

# 20 在UEFI APC上安装Hypervisor的常见问题

- 原本可以在APC上安装的Hypervisor, Boot Type选择 Legacy boot type only，由于更换了CFast卡，或者选择重新安装镜像，发现提示UEFI，不能正常安装
- 如遇到以下中列出的问题，建议使用AS4.7及以上的软件进行安装
- 案例说明
    - 如果你试图在这样的APC上安装hypervisor，你会在安装过程中收到信息，即不可能在UEFI系统上安装hypervisor。
        - ![](FILES/026Hypervisor常见问题一览/6272c0337810b13cc71f6fb441ca7533.png)
    - 在旧版本的AR中，你可以在安装过程中收到一个窗口，说没有可用的磁盘来安装Hypervisor，即使出现了未分配的分区。
        - ![](FILES/026Hypervisor常见问题一览/6facb0716d92a2d3e7bae3ebc62e7f93.png)
    - 也有可能你能在APC上以UEFI启动模式安装hypervisor，但在第一次重启hypervisor安装后，你会再次进入安装屏幕，hypervisor会想要卸载。
        - ![](FILES/026Hypervisor常见问题一览/d080bc3efdeed3114f9345ea4689461d.png)

# 21 为Hypervisor分配太多的内存

- **现象**
    - 可以在AS中配置hypervisor的内存大小。
    - ![](FILES/026Hypervisor常见问题一览/3fed4b25a65e1cc93ff3df6a62fbafb8.png)
    - 我们有不同的APC，有不同大小的DRAM内存。可能发生的情况是，为管理程序配置了太多的内存。当这种情况发生时，你会收到这个错误窗口
    - ![](FILES/026Hypervisor常见问题一览/7b50f749bf014575a3690977d528142b.png)
    - Hypervisor将不会更多的启动，GPOS也不会启动。
- **A19**:
    - 在这种情况下，有必要减少配置在 AS 中的 DRAM 内存的大小。如果需要使用更多的内存，有必要订购内部有更多DRAM内存的APC。

# 22 使用APC910 TS77-04安装Hypervisor，启动后显示器显示花屏

- **现象**
    - 用的BIOS为Q1.30 MTCX为1.25
    - 使用AS 4.6.2，AR为B4.62
    - hypervisor的ARemb在更新硬件配置后启动正常，程序正常加载。但切换到Linux系统后显示花屏。
    - ![](FILES/026Hypervisor常见问题一览/f2f134de5a2f680d4279b515be5241eb.png)
- **A20**:
    - 后将项目升级到AS4.7.2，在线更新程序，Hypervisor下AR更新成功，Linux原本的花屏现象消失

# 23 Hypervisor的驱动安装了，但内部的虚拟网口无法被找到

- A21:AS项目中的ETHinternal没有正确配置，合理配置如下：
    - ![](FILES/026Hypervisor常见问题一览/4c244741aa6a567c0b911f6bd7f9c4fe.png)

# 24 安装Hypervisor，提示Hypervisor无法安装在UEFI操作系统上

- ![](FILES/026Hypervisor常见问题一览/8d38797354450e82af32ece5d781cf88.png)
- A22:
    - 使用AS4.7，并使用Automation Runtime B4.73及以上版本进行安装。

# 25 AS4.7安装Hypervisor在Win10操作系统后，操作系统一直进入蓝屏状态，重启后仍然会进入蓝屏

- ![](FILES/026Hypervisor常见问题一览/93c7072833254ff381e464ad6254a7ef.png)
- A23:在WIndows系统上安装ADI驱动

# 26 安装Hypervisor后，屏幕花屏

- A24:
    - 有如下几种可能会导致此现象
        - 测试PPC2200时，因为BIOS的参数设置错误，导致屏幕花屏
            - BIOS的realtime environment没开
            - BIOS的Hypervisor没开
        - PPC910时，因为下载了低的Runtime，导致屏幕花屏。
        - 使用B4.62的AR

# 27 使用了性能较差的CF卡作为USB Installation Stick，导致安装异常

- ![](FILES/026Hypervisor常见问题一览/a373c683d854f2e654bcb0f0864f7a51.png)
- ![](FILES/026Hypervisor常见问题一览/f631e495278752e42c1ad89ce8370475.png)
- A25:
    - 使用USB3.0接口的U盘作为USB Installation Stick

# 28 PPC2200之类的设备，使用Debian系统，在镜像到不同屏幕上，触摸功能失效

- A26:
    - 如果使用的屏幕类型在多点触控到单点触控之间切换，使用同一个镜像，需要重新校准，否则触摸功能失效。
    - 以下简单介绍如何找到对应的驱动资源，并进行设置安装。
    - 确认Debian系统上安装了Touch Screen驱动，如果没有安装，可去贝加莱官网进行下载获取
    - ![](FILES/026Hypervisor常见问题一览/012047c65d950e2811ebb34a11a821d4.png)
    - ![](FILES/026Hypervisor常见问题一览/26434ffe4d14265b7858932371f5e964.png)
- 使用Root权限安装完成后，在启动项列表中找到Touch Screen。
    - ![](FILES/026Hypervisor常见问题一览/7c96a998b8ebf75a51994e89abfc631d.png)
- 先点击Test all，再Apply，即解决屏幕的触摸不起作用的问题。
    - ![](FILES/026Hypervisor常见问题一览/852ad73d07168d5bae924b66cbe14dc1.png)
- 若发现屏幕上点击有偏移，可在此页面，先Assign屏幕，再Calibrate校准屏幕。
    - ![](FILES/026Hypervisor常见问题一览/20a72c9ef4ddd941516985a735469910.png)
- 关于Linux上驱动的具体使用方式，可下载对应的文档，了解更多。
    - ![](FILES/026Hypervisor常见问题一览/99ef5b34aa640c23dd411b10f103f1b2.png)

# 29 安装好Hypervisor后的Windows系统如何再次分区？

- A27:
    - 需要先卸载Hypervisor，再通过Windows磁盘管理或DiskGenius软件进行分区，否则会提出如下报错。
    - ![](FILES/026Hypervisor常见问题一览/7d15d2cc69fba861313dbfdf531f72ca.png)

# 30 安装Hypervisor后提示安装成功，但实际Hypervisor没有启动，ETH口无法连上。

- A28:
- BIOS启动项设置错误，1st Boot Device需要调整为BR Hypervisor，（选择设置后能够看到此选项）
    - ![](FILES/026Hypervisor常见问题一览/d656f4fd761b489b20bf1447e19cb1a7.png)

# 31 在APC910-QM77上安装Hypervisor报错提示Virtualization is disabled by the firmware

- ![](FILES/026Hypervisor常见问题一览/4fbab6dc5bdf44743ba506f455f1e120.png)
- A29:
    - BIOS与Firmware版本过低，需要更新至最新。操作参考[此处](#FAQ11)。

# 32 5ACPCE.ETH4-00卡能否支持Hypervisor？

- A30:
    - 支持在Windows/Linux上使用
    - ARemb上无须配置
    - 使用贝加莱BR Linux(debian 10)，无须额外装驱动，卡插上即可直接使用。

# 33 在操作系统为Debian 10上的APC910 TS17-04设备上安装Hypervisor，提示如下报错

- ![](FILES/026Hypervisor常见问题一览/9b05f200a6f75ec683f172219add26fa.png)
- A31:
    - 原因为Linux下的驱动没有安装好。
    - 使用最新的Automation Runtime，创建Hypervisor的USB Installation Stick，可从中获得最新的Linux驱动，将驱动完全安装后，再安装Hypervisor。
    - 详情参考 [Hypervisor使用助手 > 安装与使用 > Linux_Hypervisor安装指导手册 > 驱动安装 | Linux平台上安装Hypervisor驱动 (brhelp.cn)](https://hypervisor.brhelp.cn/index.html?setup10.html)

# 34 安装Hypervisor驱动时，提示A backup of the original boot loader already exists.

- **现象**
    - ![](FILES/026Hypervisor常见问题一览/d13a798d6b394026786d6031d04200b7.png)
- **原因**:
    - 原因是未分配的分区不在磁盘上最末尾，或者boot loader信息错了。
    - ![](FILES/026Hypervisor常见问题一览/f055ee852269e4af53381a0aaa2ce562.png)
- **解决方式**
    - 重装Windows/Linux，重新安装后，有必要正确地分割磁盘，使未分配的分区成为列表中的最后一个分区。

# 35 原先安装正常使用的Hypervisor，卸载安装其他版本的Hypervisor，出现 The original boot loader could not be backuped

- ![](FILES/026Hypervisor常见问题一览/5ae0cc15f5553871bedbb42feb5e9409.png)
- A33: 更换高版本AR解决。
- 具体情况如下：
    - 在Win 10 2016上安装Hypervisor （AS4.7 AR:H4.73 )正常使用，但偶发出现网口丢失问题
    - 升级高版本Hypervisor (AS4.12 AR:B4.93)，无法安装，提示The original boot loader could not be backuped
    - 重新安装旧版本 (AS4.7 AR:H4.73)，能够正常安装
    - 使用更新的版本(AS4.12 AR:E4.93)，能够正常安装

# 36 Hypervisor在USB更新程序后无法启动显示License is not valid

- ![](FILES/026Hypervisor常见问题一览/7f069a11f7c5b65ac3ded490ad2dc3ec.png)
- A34: 更换更新用的U盘后解决。

# 37 给一台全新的硬件安装Hypervisor提示Uninstall

- ![](FILES/026Hypervisor常见问题一览/633693e465a3e41fa09ca7c8ee75f119.png)
- A35:
    - 使用DiskGenius软件检查磁盘分区情况，信息如下，可见分了一个D盘，并且信息为扩展分区，Hypervisor安装的区域为硬盘的末尾，且前面分区不能为扩展分区
        - ![](FILES/026Hypervisor常见问题一览/c5fdc7ce6a5538babc180881f7e04086.png)
    - 解决方式为调整分区
        - ![](FILES/026Hypervisor常见问题一览/3d975336f54113f96e2698d2796dacd6.png)
- 重新安装Hypervisor即显示正常
    - ![](FILES/026Hypervisor常见问题一览/9ffa39ce6509410480c761f832bca3ea.png)

# 38 安装过程中 Hypervisor 重启几次后，卡在/OS/1 Booting runtime 0 状态

- 现象
    - ![](FILES/026Hypervisor常见问题一览/73e802585a4ead7d4c321328e3556b94.png)
    - 或者如下界面
    - ![](FILES/026Hypervisor常见问题一览/37f20a975977a1532d625a9978c8498c.png)
- A36:
    - 需要在线通过Automation Studio连上Hyperviosr的ARemb端，进行更新程序后解决。

# 39 U盘安装Hypervisor，在系统选择从U盘启动时提示BOOTMGR is missing

- 现象
    - ![](FILES/026Hypervisor常见问题一览/33fe0d517f29f0b916e19c1e2aff30ba.png)
- A37:
    - U 盘坏了，换个 U 盘（建议使用 USB 3.0 及以上的接口的 U 盘，使用 2.0 接口的 U 盘，可能会导致安装失败 )

# 40 安装Hypervisor提示Hypervisor boot failed.

- **现象**
    - ![](FILES/026Hypervisor常见问题一览/7b3e0f0247c13857e2de0717d5bb7493.png)
- **A38**:
    - Hypervisor的分区有问题，windows里面shink没用，Hypervisor安装时仍会提示uninstall，无法安装
    - 重新用DiskGenius软件删除重建选主分区，确保磁盘最后一个分区是主分区，就可以install了。

# 41 安装卡在30%，出现欢迎访问Buildroot的信息

- **现象**
    - 在安装过程中，安装程序冻结在30%，并出现“Welcome to Buildroot"和“Buildroot login:”。重启后再开始安装，你会看到 boot loader已经存在的信息
    - ![](FILES/026Hypervisor常见问题一览/image-20231129143918745.png)
- **可能的原因和补救措施**
    - 未分配的分区不是列表中的最后一个，有可能是用"Free space preceding"而不是"New size"创建的自由空间。
    - Linux可能需要重新安装。

# 42 在APC3100上安装Hypervisor提示You cannot install B&R Hypervisor on a UEFI system when you have booted the USB install stick with legacy.

- **现象**
    - ![](FILES/026Hypervisor常见问题一览/image-20231129153224329.png)
- 硬件：
    - 5APC3100_KBU2_000
- 操作系统：
    - Windows 10 IoT Enterprise 2019 LTSC
- 开发环境
    - AS4.10 E4.93
- 磁盘信息
    - ![](FILES/026Hypervisor常见问题一览/image-20231129153834448.png)
- **解决方式**
    - ![](FILES/026Hypervisor常见问题一览/image-20231129154049047.png)

# 43 使用AS4.10，Hypervisor安装提示 No EFI system partition (ESP) found

- **基本参数**
    - 硬件：APC3100
    - AR版本：G4.91
    - AS版本：AS4.10
    - BIOS - Boot Type为UEFI Boot Type
- **现象**
    - 安装Linux系统（Ubuntu 16.04）后，再安装Hypervisor后，提示No EFI system partition （ESP) found
    - ![](FILES/026Hypervisor常见问题一览/image-20231228125638875.png)
- **可能的原因**
    - CFast卡内的文件系统异常，需要使用Disk Genius软件调整
- **解决方式**
    - 1) 格式化卡：使用Diskgenius软件，将卡删除所有分区，并格式化（默认NTFS格式）
    - 2) 将格式化后的卡，进行磁盘分区操作，分为以下三个部分：
        - ESP：EFI格式(300MB)
        - 本地磁盘E：228GB
        - 剩余磁盘：闲置空区域
    - 3) 重新安装Linux系统，再使用同样的版本安装Hypervisor正常

# 44 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2023-12-28 | YZY | 更新   |
| 2024-03-19 | YZY | 格式调整 |
