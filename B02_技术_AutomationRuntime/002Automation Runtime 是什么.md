> Tags: #AR

# B02.002.Automation Runtime 是什么？

> Automation Runtime （简称为 AR），即在贝加莱硬件中运行的实时精简操作系统，基于VxWorks。

> Automation Runtime 可以理解为类似于Windows/Linux的操作系统，它本体只有几十MB，但其拥有极强的实时性以及丰富的软件功能，使用Automation Runtime，你可以极大的利用硬件资源，用较低的CPU能耗，运行相当复杂的功能。

- Automation Runtime 实时操作系统是 Automation Studio 开发软件编译项目后输出至CF卡/CFast卡中的操作系统。其构成​​了允许应用程序在目标系统上运行的软件内核。
    - 保证所用硬件的最高性能
    - 在所有贝加莱目标系统上运行
    - 使应用程序独立于硬件
    - 贝加莱目标系统之间的应用程序易于移植
    - 支持所有相关的编程语言，例如IEC 61131-3 语言、C、C++
    - 符合IEC 61131-3的丰富函数库以及扩展的贝加莱自动化库
    - 集成在Automation NET 中。通过函数调用或在 Automation Studio™ 中配置访问所有网络和总线系统
- B&R Automation Runtime 完全嵌入相应的目标系统（安装了 Automation Runtime 的硬件）。
- 因此，它使应用程序能够访问 I/O 系统（也通过现场总线）和其他设备，例如接口和网络。
