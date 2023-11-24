> 013编写 C 与 Cpp 编译提示 undefined reference to sbrk

- [1 现象](#1%20%E7%8E%B0%E8%B1%A1)
- [2 原因](#2%20%E5%8E%9F%E5%9B%A0)

# 1 现象

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

# 2 原因

- 在贝加莱 PLC 中编写 C/C++代码，有部分函数无法使用，例如
    - printf
    - `_Exit`
    - fgets
    - fopen
- 请在 Automation Help 中的 Programming - Program - ANSI C/C++ - Using functions of C runtime libraries 中确认使用相关函数的限制
    - ![](FILES/013编写C与Cpp代码编译提示undefined%20reference%20to%20sbrk/image-20231124201628991.png)
- 若不能使用，请检查 include 的头文件是否正确，并其中是否相关的接口实现，在代码中屏蔽相关代码，换用其他的实现方式
