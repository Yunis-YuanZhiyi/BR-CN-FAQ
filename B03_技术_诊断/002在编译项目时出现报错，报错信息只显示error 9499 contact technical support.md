# 002在编译项目时出现报错，报错信息只显示error 9499 contact technical support
Tags：编译报错
![](FILES/002在编译项目时出现报错，报错信息只显示error%209499%20contact%20technical%20support/image-20230314133755023.png)
A： 

这种报错没有详细的错误信息，通常是因为AS安装不完整造成的。可以参照如下方法进行解决：

- a. 重新获得项目文件，删除项目文件夹下的Temp，Binary文件夹，重新全编译
- b. 两次全编译解决此问题。第一次编译再按取消，再按一次全编译。
- c. 安装SP升级包升级Automation Studio版本到最新版本 （**2020.7.31**）
    - 可前往贝加莱官网，找到Home - Downloads - Software - Automation Studio - Automation Studio 4.7，下载V4.7 AS Upgrade (4.7.7.74_SP)安装包
- d. 完全卸载当前电脑上的AS并重装，保证重装的AS路径和先前AS的安装路径一致
- e. 重新解压他人发送过来的项目，重新编译即解决（**2023.3.14**）