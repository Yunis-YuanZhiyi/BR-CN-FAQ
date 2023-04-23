## 问题描述
程序里定义两个全局数据类型列表，其中A_sty中包含了B_sty，这种情况如果加入一个c语言的program编译就会报错，加入st语言的program就没问题。

![](FILES/008C语言使用结构体套用结构体报错field%20xx%20has%20incomplete%20type/image-20230421155525823.jpeg)



## 解决方式

取消设置中的下面选项：

![](FILES/008C语言使用结构体套用结构体报错field%20xx%20has%20incomplete%20type/image-20230421155537025.png)

在.c文件里 手写头文件引用顺序