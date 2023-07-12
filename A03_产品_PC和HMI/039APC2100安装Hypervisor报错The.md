## 问题描述
对5APC2100进行Hypervisor安装时，报错“The PCI device specified in section[/PCI/1]cannot be explicitly assigned because it is configured for other purposes
![](FILES/039APC2100安装Hypervisor报错The/image-20230711152859544.png)



## 解决方式
使用AS扫描到该设备，连接上该设备，transfer程序，transfer结束后，会重启设备，重启后正常进入系统。
![](FILES/039APC2100安装Hypervisor报错The/image-20230712162103563.jpeg)








