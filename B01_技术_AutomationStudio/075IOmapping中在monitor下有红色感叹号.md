# 现象
在 Monitor 下，看到感叹号，Process variable Value 的值是 Error
![](FILES/075IOmapping中在monitor下有红色感叹号/image-20230823230854503.png)

# 原因
此通道绑定的变量（即 Process variable 通道中绑定的值），并没有在程序中调用。
