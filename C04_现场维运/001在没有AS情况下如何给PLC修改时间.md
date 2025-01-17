> Tags: #对时 #维护

- [1 C04.001.在没有AS情况下如何给PLC修改时间](#_1-c04001%E5%9C%A8%E6%B2%A1%E6%9C%89as%E6%83%85%E5%86%B5%E4%B8%8B%E5%A6%82%E4%BD%95%E7%BB%99plc%E4%BF%AE%E6%94%B9%E6%97%B6%E9%97%B4)
- [2 目的](#_2-%E7%9B%AE%E7%9A%84)
- [3 所需软件](#_3-%E6%89%80%E9%9C%80%E8%BD%AF%E4%BB%B6)
- [4 操作步骤](#_4-%E6%93%8D%E4%BD%9C%E6%AD%A5%E9%AA%A4)

# 1 C04.001.在没有AS情况下如何给PLC修改时间

# 2 目的

- 在没有安装Automation Studio软件的情况下，如何给PLC对时

# 3 所需软件

- 需要在电脑上安装PVI软件
- 贝加莱官网下载链接：
    - [PVI Development Setup | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/downloads/software/automation-netpvi/pvi-development-setup/)
    - 路径：`Home - Downloads - SoftwareAutomation - NET/PVI`

# 4 操作步骤

- <span style="background:#A0CCF6">1___</span>安装完成PVI软件后，找到Runtime Utility Center
    - ![](FILES/001在没有AS情况下如何给PLC修改时间/image-20230310212701616.png)
- <span style="background:#A0CCF6">2___</span>选择Create, modify and execute projects （.pil）
    - ![](FILES/001在没有AS情况下如何给PLC修改时间/image-20230310212725605.png)
- <span style="background:#A0CCF6">3___</span>选择连接PLC，选择TCP IP后，再编辑需要连接的PLC的IP地址，以及对应的端口号（默认11159，如果通不上换成11169）
    - ![](FILES/001在没有AS情况下如何给PLC修改时间/image-20230310212838580.png)
- <span style="background:#A0CCF6">4___</span>选择Set date and time, 选择正确的日期与时间
    - ![](FILES/001在没有AS情况下如何给PLC修改时间/image-20230310212906283.png)
- <span style="background:#A0CCF6">5___</span>点击执行按钮
    - ![](FILES/001在没有AS情况下如何给PLC修改时间/image-20230310213121277.png)
