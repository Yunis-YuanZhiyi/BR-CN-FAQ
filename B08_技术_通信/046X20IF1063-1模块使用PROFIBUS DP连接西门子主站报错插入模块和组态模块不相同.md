## 问题描述

如图，贝加莱这边配置的是8 words out，西门子这边配置了8 words in

![](FILES/046X20IF1063-1模块使用PROFIBUS%20DP连接西门子主站报错插入模块和组态模块不相同/image-20230724151854846.png)


![](FILES/046X20IF1063-1模块使用PROFIBUS%20DP连接西门子主站报错插入模块和组态模块不相同/image-20230724151834784.jpeg)

![](FILES/046X20IF1063-1模块使用PROFIBUS%20DP连接西门子主站报错插入模块和组态模块不相同/image-20230724151846177.jpeg)

## 解决方法

与西门子设备进行DP通信需要in和out的一致性，也就是AS这边配置了8 words in，西门子那边也要配置成8 words in。

