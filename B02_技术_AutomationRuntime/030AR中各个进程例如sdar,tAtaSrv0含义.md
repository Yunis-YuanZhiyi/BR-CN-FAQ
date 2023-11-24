> AR 中各个进程例如 sdar,tAtaSrv0含义

#进程
# 使用前提
- CPU 任务执行的进程分析均依赖于 Profiler 功能

# TcIdleFiller
- 空闲任务进程
- ![](FILES/030AR中各个进程例如sdar,tAtaSrv0含义/image-20231124184550180.png)
- 在计算 CPU 占用率时，此进程算作 IDLE 资源
- "TcIdleFiller "正在使用强制空闲时间（Timing / Idle Time）的剩余部分，这些时间未被其他系统任务占用。
- 即意味着在使用此处分配但未使用的资源
- ![](FILES/030AR中各个进程例如sdar,tAtaSrv0含义/image-20231124184647822.png)
- 🔴 目前（2023），SDM(System Diagnostics Manager) 中统计的 CPU 占用率，把 TcIdleFiller 也算作是负载。请以 Profiler 中的数据显示为准。

# UnknownCyclic
- 如果进程任务是在 Profiler 开始计算时创建的，则此任务会以 UnknownCyclic 任务名称的方式出现。
## 解决方式
- 设置 “Buffer for created user tasks” 给出了可用于存储有关动态创建的进程任务以及在运行期间传输的任务的信息的缓冲区数量。
- 软件树中任务的顺序就是 PLC 上执行任务的顺序，因此，如果查看任务类中的前后任务，通常就能知道 "未知循环 "任务是哪个任务。
- ![](FILES/030AR中各个进程例如sdar,tAtaSrv0含义/image-20231124185827566.png)

# interrupt 说明
- **B&R I/O 总线**（如 X2X Link 或 POWERLINK）使用的中断在 Profiler 中使用接口名称（IF6、IF3、SS1. IF1…）。
- 由 VxWorks 驱动程序处理的中断没有完整的信息提供
- **SystemTick** 的定时器中断很容易识别，因为它在一个系统周期内恰好出现 2 次，时间恰好是系统周期时间的一半。
- Interrupt 27 仅适用于 X90CP174硬件
#  `IE#n`
- 执行循环任务中的 INIT 初始化部分代码的进程
# TimeSync
- 若占用太多的 CPU 资源，并伴随着 30993 报警，请升级 AR 至以下版本以上
- D4.73
- C4.83
- D4.90
- B4.91
- A4.92


# tAtaSvc0
- VxWorks 操作 ATA Device 的进程，例如对常见的 CF 卡进行读、写、Ioctl
- 若此进程占用非常高的负载，请注意是否有大量的文件读写操作，是否 FTP 服务被第三方高频请求
- ![](FILES/030AR中各个进程例如sdar,tAtaSrv0含义/image-20231124195033718.png)


# sdar
- SDM（System Diagnostics Manager） 服务消耗的资源

