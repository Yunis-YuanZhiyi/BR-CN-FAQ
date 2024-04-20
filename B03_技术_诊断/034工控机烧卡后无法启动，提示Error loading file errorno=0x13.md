> Tags: #工控机 #故障诊断 

# 1 B03.034-工控机烧卡后无法启动，提示Error loading file errorno=0x13
- 使用APC2200硬件，使用二进制烧卡包烧卡，设备无法启动，报错信息为
    - Cannot open"error".
    - Error loading file: errno = 0x13.
    - Can't load boot file!!
- 将显示屏通过HDMI/DVI线连接工控机，可见如下报错
    - ![](FILES/034工控机烧卡后无法启动，提示Error%20loading%20file%20errorno=0x13/image-20240420130229859.png)
- 系统未进SERVICE模式，无法通过SDM查看到故障原因与相关信息

# 2 原因与解决方式
- 实际硬件中的CPU型号与项目配置的CPU型号不一致。
- 此问题的现象为，若APC系列硬件的CPU版本，配置硬件与实际硬件的差异过大，则上电后会无法启动，系统不会进入SERV模式，在显示器上可能可见 errno = 0x13 报错
    - 例如：软件项目配置了APC910，实际硬件为APC2200
- 若配置硬件与实际硬件差异不大，例如均是APC2200，CPU型号是同系列的，则能够启动后进入SERV，可通过SDM查看具体的差异进行修正。
    - ![](FILES/034工控机烧卡后无法启动，提示Error%20loading%20file%20errorno=0x13/image-20240420133552098.png)



# 3 更新日志
| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-04-17 | QZY<br>YZY | 初次创建 |
