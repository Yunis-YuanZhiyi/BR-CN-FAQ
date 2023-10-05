# 004在下载程序时，提示Automation runtime target mismatch，如何解决？

Tags：Automation Runtime、target mismatch

# 现象

- 点击 **Transfer** 按钮（或者按 `CTRL + F5`）的时候提示如下信息，无法实现在线更新
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005120811247.png)-

# 原因

- <span style="background:#A0CCF6">Automation Studio</span> 在线传输的时候会检查被传输的 PLC 的实际硬件型号与当前<span style="background:#A0CCF6"> Automation Studio</span> 所配置的 PLC 硬件型号是否一致，如果不一致，则会提示 Automation runtime target mismatch。
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005124322350.png)
    - 需要注意，是否带涂层的硬件分别属于两个不同的硬件类型，例如 `X20CP1585` 和 `X20cCP1585` 是不同的控制器。
- 解决思路：更改项目 <span style="background:#A0CCF6">Automation Studio </span>硬件组态中的控制器型号，重新下载程序即可。

# 解决方式
- 1. 检查实际 AS 软件连接的硬件是什么具体型号
- 2. 确认 AS 项目中 Physical View 中的 CPU 型号是否一致
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005124617565.png)


