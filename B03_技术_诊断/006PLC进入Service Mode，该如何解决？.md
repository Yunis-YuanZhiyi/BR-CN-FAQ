# 006PLC进入Service Mode，该如何解决？
Tags： Service Mode
A：

PLC进入Service Mode的可能性较多。较为常见的原因是程序中的硬件组态与实际硬件不符合。
常见的排查流程如下：

1. 上电，将PLC连接电脑。
2. 在AS中打开Logger，直接查看错误信息。并根据错误信息的提示进行修改。
3. 冷重启或热重启PLC。