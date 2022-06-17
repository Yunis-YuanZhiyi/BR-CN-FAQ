# 如何使用PVI Snapshot功能诊断PVI连接情况
## 问题描述
如何使用PVI Snapshot功能诊断PVI连接情况，任何使用到PVI连接B&R控制器的软件（如AS，或者第三方使用到PVI接口的软件）如遇到通讯问题，都可以用以下方法进行诊断。
使用其他通讯接口，如Modbus TCP，OPC UA，POWERLINK等则不适用于改方法检查

## 解决方案

1. 生成PVI snapshot文件

打开PVI monitor，选择Options菜单栏下的PVI Diagnostics

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617141813.png)


按下Path按钮

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617141907.png)


设定PVI Snapshot存储文件名及存储路径

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617141916.png)


按下Snapshot按钮

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617141926.png)


此时软件不会有任何提示，但是该文件已在设定的路径下产生

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617141935.png)



2. 查看PVI snapshot文件

打开PVI Snapshot Viewer

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617142010.png)

通过Open Snapshot File打开刚才生成的snap文件

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617142023.png)

左侧为PVI通讯的树形结构，本例的场景为使用AS打开Sample里的mappService highlight案例程序，并打开Simulation后监控gCoffeeMainLogic这个全局结构体变量

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617142030.png)


可以在Snapshot文件中的Process Objects->Pvi->AS_Line_xxxxxxx下查看PVI正在连接的情况

![Img](./FILES/023如何使用PVI%20Snapshot功能诊断PVI连接情况.md/img-20220617142046.png)
