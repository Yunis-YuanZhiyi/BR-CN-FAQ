> Tags: #ncaction #运动控制 #ACOPOS_P3

# B06.032-贝加莱ACOPOS_P3支持ncaction吗

- 标准的ACP 10轴ncaction命令仍然完全工作。

# ACOPOS P3轴控底层特点

- ACOPOS P3 内部仍兼容使用 ncaction。
- ACP10中的PLCopen功能块只在后台调用ncaction。
- 唯一需要注意的是轴驱动程序是ACP10而不是ARNC0。
    - 早期，ARNC0 Manager 可直接用于（通过所谓的 ARNC0 单轴）控制驱动器。
    - 这种方法在 V3.xx.x 中被取消，因此此类应用程序在 P3 上确实无法运行。

# 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2024-02-02 | YZY | 初次创建 |
