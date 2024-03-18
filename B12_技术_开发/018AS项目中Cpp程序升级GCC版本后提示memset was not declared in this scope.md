> Tags: #cpp #gcc

- [1 现象](#1%20%E7%8E%B0%E8%B1%A1)
- [2 解决方式](#2%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [3 更新日志](#3%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# B12.018-AS项目中Cpp程序升级GCC版本后提示memset was not declared in this scope

# 1 现象

- 原先在GCC 4.1.2编译正常的C++项目，在升级了GCC版本至6.3.0之后，编译异常报错，报错信息如下
- ![](FILES/018AS项目中Cpp程序升级GCC版本后提示memset%20was%20not%20declared%20in%20this%20scope/image-20231225220406553.png)
    - `'_M_cat' was not declared in this scope`
    - `'category' was not declared in this scope`
    - `error_category' does not name a type`
    - `'memcpy' was not declared in this scope`
    - `'memset' was not declared in this scope`
    - `'strcat' was not declared in this scope`
    - `'strcpy' was not declared in this scope`
- 原先正常在GCC 4.1.2下编译正常的版本与cpp头文件信息中引用了
    - `#include <sstream>`
    - `#include <string>`

# 2 解决方式

- 由于不同GCC版本，函数的实现头文件有变更，需要进行调整。
- 详情见以下说明
    - [cplusplus.com/reference/cstring/?kw=string.h](https://cplusplus.com/reference/cstring/?kw=string.h)
    - `# <cstring> (string.h)`
- 解决方式操作
- ![](FILES/018AS项目中Cpp程序升级GCC版本后提示memset%20was%20not%20declared%20in%20this%20scope/image-20231225221212530.png)

# 3 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2023-12-25 | YZY | 初次创建 |
