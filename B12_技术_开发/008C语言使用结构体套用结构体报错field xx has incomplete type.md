> Tags: #cpp #c

- [1 B12.008.C 语言使用结构体套用结构体报错 field xx has incomplete type](#_1-b12008c-%E8%AF%AD%E8%A8%80%E4%BD%BF%E7%94%A8%E7%BB%93%E6%9E%84%E4%BD%93%E5%A5%97%E7%94%A8%E7%BB%93%E6%9E%84%E4%BD%93%E6%8A%A5%E9%94%99-field-xx-has-incomplete-type)
- [2 问题描述](#_2-%E9%97%AE%E9%A2%98%E6%8F%8F%E8%BF%B0)
- [3 解决方式](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)

# 1 B12.008.C 语言使用结构体套用结构体报错 field xx has incomplete type

# 2 问题描述

- 程序里定义两个全局数据类型列表，其中 A_typ 中包含了 B_typ，这种情况如果加入一个 c 语言的 program 编译就会报错，加入 st 语言的 program 就没问题。
    - ![](FILES/008C语言使用结构体套用结构体报错field%20xx%20has%20incomplete%20type/image-20230421155525823.jpeg)

# 3 解决方式

- 取消设置中的下面选项：
    - ![](FILES/008C语言使用结构体套用结构体报错field%20xx%20has%20incomplete%20type/image-20230421155537025.png)
- 在.c 文件里，屏蔽默认的 ` #include <AsDefault.h>`
    - 手写头文件引用顺序
    - 例如

```c
#include <bur/plctypes.h>  
#include <math.h>  
#include <GlobalFFTtyp.h>  
#include <GlobalFFtvar.h>  
#include <FFTtyp.h>  
#include <FFTvar.h>
```
