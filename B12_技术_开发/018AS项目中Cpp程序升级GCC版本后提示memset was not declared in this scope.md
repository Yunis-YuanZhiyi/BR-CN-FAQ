> Tags: #cpp #gcc

- [1 B12.018-AS项目中Cpp程序升级GCC版本后提示memset was not declared in this scope](#_1-b12018-as%E9%A1%B9%E7%9B%AE%E4%B8%ADcpp%E7%A8%8B%E5%BA%8F%E5%8D%87%E7%BA%A7gcc%E7%89%88%E6%9C%AC%E5%90%8E%E6%8F%90%E7%A4%BAmemset-was-not-declared-in-this-scope)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 解决方式](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B12.018-AS项目中Cpp程序升级GCC版本后提示memset was not declared in this scope

# 2 现象

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

# 3 解决方式

- 由于不同GCC版本，函数的实现头文件有变更，需要进行调整。
- 详情见以下说明
    - [cplusplus.com/reference/cstring/?kw=string.h](https://cplusplus.com/reference/cstring/?kw=string.h)
    - `# <cstring> (string.h)`
- 解决方式操作
- ![](FILES/018AS项目中Cpp程序升级GCC版本后提示memset%20was%20not%20declared%20in%20this%20scope/image-20231225221212530.png)

# 4 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2023-12-25 | YZY | 初次创建 |
