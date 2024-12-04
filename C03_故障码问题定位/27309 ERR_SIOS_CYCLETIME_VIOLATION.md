# 27309 ERR_SIOS_CYCLETIME_VIOLATION

- Error constant
    - ERR_SIOS_CYCLETIME_VIOLATION
- 短文本
    - AR-SIOS: Failed system tick event.
- 错误描述
    - I/O调度程序检测到失败的系统滴答事件。I/O调度器的起始点被中断、高优先级任务或自身延迟，以至于系统滴答事件无法及时响应。CPU可能不够快，无法满足所需的系统滴答周期时间。
- 纠错建议
    - 在APC/PPC上，必须在BIOS设置中启用 “实时环境Realtime Environment”。
    - 增加系统滴答周期时间 (System tick Cycle time) 降低了系统的实时要求。

# 现象

- PPC系列工控机，偶发SERV，并屏幕蓝屏。

# 解决方式

- PPC系列工控机由屏幕与背包控制器组成，两者通过螺丝固定连接。
- 发现出现问题的工控机的连接螺丝有些松动。
- 通过拧紧螺丝，此问题不再出现。
