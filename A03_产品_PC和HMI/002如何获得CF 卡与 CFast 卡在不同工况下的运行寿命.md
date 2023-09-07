# 002如何获得CF 卡与 CFast 卡在不同工况下的运行寿命

- Tags：存储卡、寿命
- A：

# 方法一：

- 使用ArStorage库获取存储介质寿命情况。
- 注1：参见Automation Studio帮助 Guid ID：15e55f50-8140-49b8-b7c0-8c6ea1dc8a65。
- 注2：该库仅针对SG4的系统，AR 需在V4.90或更高版本中使用。

# 方法二：

- 对于具有S.M.A.R.T 功能的 CF/CFast 卡可通过 swissbit 公司的 SBLTM 软件获取 CF 卡运行1个周期的 AEC 差值，再根据 CF/CFast 卡的 Clear/Write cycles 值，
- 从而计算出 CF/CFast 卡大致运行寿命：
    - 1)	通过s.m.a.r.t读取数据存储介质的“平均擦除计数”
    - 2)	在规定的一段时间内(如1周)，用相关的数据存储介质完全操作系统。
    - 3)	通过“平均擦除计数”确定使用的擦除周期。
    - 4)	根据最大保证写/擦除周期(MLC： 3000, SLC： 100,000)确定预期的使用寿命。
    - 5)	SBLTM 软件（SBLTM – Life Time Monitoring Tool for Windows）不是贝加莱官方软件，如有需要请访问 [适用于工业应用的安全和存储解决方案 - Swissbit](https://www.swissbit.com/zh/) 注册后下载获取。
- ⭐注1：CF 卡的S.M.A.R.T 数值只能通过具有 CF 卡槽与硬盘卡槽的贝加莱工控机读取（例如把 CF 卡插在 ACP 810 的 CF 卡槽中，APC 安装 Windows 系统，APC 上运行 SBLTM 软件获取信息。）。CFast 卡的S.M.A.R.T 数据可通过普通电脑获取。因为 SBTML 软件只能使用在 IDE 控制器平台上，CF 卡是通过 USB 适配器介入笔记本电脑，因此会出现无法识别的现象。
- 注2：参见Automation Studio帮助 Guid ID：6c5d0a49-0468-4100-91c0-f30712abd55a；
