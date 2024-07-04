> Tags: #cpp #c

- [1 B12 .013.编写 C 与 Cpp 编译提示 undefined reference to sbrk](#_1-b12-013%E7%BC%96%E5%86%99-c-%E4%B8%8E-cpp-%E7%BC%96%E8%AF%91%E6%8F%90%E7%A4%BA-undefined-reference-to-sbrk)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 原因](#_3-%E5%8E%9F%E5%9B%A0)

# 1 B12 .013.编写 C 与 Cpp 编译提示 undefined reference to sbrk

# 2 现象

- 编译项目时提示如下报错：
- undefined reference to 'sbrk'
- undefined reference to ' `_exit` '
- undefined reference to 'close'
- undefined reference to 'fstat'
- undefined reference to 'lseek'
- undefined reference to 'read'
- undefined reference to 'times'
- undefined reference to 'write'
- ![](FILES/013编写C与Cpp代码编译提示undefined%20reference%20to%20sbrk/image-20231124200036147.png)

# 3 原因

- 在贝加莱 PLC 中编写 C/C++代码，有部分函数无法使用，例如
    - printf
    - `_Exit`
    - fgets
    - fopen
- 请在 Automation Help 中的 Programming - Program - ANSI C/C++ - Using functions of C runtime libraries 中确认使用相关函数的限制
    - [在线英文帮助 → B&R Online Help (br-automation.com)](https://help.br-automation.com/#/en/4/programming%2Fprograms%2Fansic%2Fprogrammingmodel_programs_ansic_reservedkeywords.html)
    - ![](FILES/013编写C与Cpp代码编译提示undefined%20reference%20to%20sbrk/image-20231124201628991.png)
- 若不能使用，请检查 include 的头文件是否正确，并其中是否相关的接口实现，在代码中屏蔽相关代码，换用其他的实现方式
