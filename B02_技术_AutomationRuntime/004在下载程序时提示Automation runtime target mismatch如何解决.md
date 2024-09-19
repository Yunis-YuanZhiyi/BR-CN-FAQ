> Tags: #AR

- [1 B02.004.在下载程序时，提示Automation runtime target mismatch，如何解决？](#_1-b02004%E5%9C%A8%E4%B8%8B%E8%BD%BD%E7%A8%8B%E5%BA%8F%E6%97%B6%EF%BC%8C%E6%8F%90%E7%A4%BAautomation-runtime-target-mismatch%EF%BC%8C%E5%A6%82%E4%BD%95%E8%A7%A3%E5%86%B3%EF%BC%9F)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 原因](#_3-%E5%8E%9F%E5%9B%A0)
- [4 解决方式](#_4-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)

# 1 B02.004.在下载程序时，提示Automation runtime target mismatch，如何解决？

# 2 现象

- 点击 **Transfer** 按钮（或者按 `CTRL + F5`）的时候提示如下信息，无法实现在线更新
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005120811247.png)-

# 3 原因

- <span style="background:#A0CCF6">Automation Studio</span> 在线传输的时候会检查被传输的 PLC 的实际硬件型号与当前<span style="background:#A0CCF6"> Automation Studio</span> 所配置的 PLC 硬件型号是否一致，如果不一致，则会提示 Automation runtime target mismatch。
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005124322350.png)
    - 需要注意，是否带涂层的硬件分别属于两个不同的硬件类型，例如 `X20CP1585` 和 `X20cCP1585` 是不同的控制器。
- 解决思路：更改项目 <span style="background:#A0CCF6">Automation Studio </span>硬件组态中的控制器型号，重新下载程序即可。

# 4 解决方式

- 1. 检查实际 AS 软件连接的硬件是什么具体型号
- 2. 确认 AS 项目中 Physical View 中的 CPU 型号是否一致
- ![](FILES/004在下载程序时提示Automation%20runtime%20target%20mismatch如何解决/image-20231005124617565.png)
