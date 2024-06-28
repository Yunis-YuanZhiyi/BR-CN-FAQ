> Tags: #ARSim #Windows

- [1 090ARSim启动时报错提示DEP_Data Execution Prevention](#_1-090arsim%E5%90%AF%E5%8A%A8%E6%97%B6%E6%8A%A5%E9%94%99%E6%8F%90%E7%A4%BAdep_data-execution-prevention)
- [2 解决方式：Windows上禁用DEP](#_2-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%EF%BC%9Awindows%E4%B8%8A%E7%A6%81%E7%94%A8dep)
- [3 如何确认DEP已被关闭](#_3-%E5%A6%82%E4%BD%95%E7%A1%AE%E8%AE%A4dep%E5%B7%B2%E8%A2%AB%E5%85%B3%E9%97%AD)
- [4 参考链接](#_4-%E5%8F%82%E8%80%83%E9%93%BE%E6%8E%A5)
- [5 更新日志](#_5-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 090ARSim启动时报错提示DEP_Data Execution Prevention

- 要运行 ARsim，必须禁用或不启用所有 Windows 程序或服务的数据执行防护功能。
- DEP 是 Windows 10 默认启用的一项安全功能。启用该功能后，在启动模拟程序时会出现 ar000loader 错误，ARSim 无法执行，报错如下
    - Termination: DEP (Data Execution Prevention) enabled. See documentation for more information!
    - ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628085046760.png)

# 2 解决方式：Windows上禁用DEP

- 打开 Windows 安全应用程序 → 应用程序和浏览器控制 → 选择 "漏洞利用保护设置 Exploit protection"：
    - ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628090802416.png)
- 将DEP （Data Execution Prevention）选项设置为 Off by default
    - ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628090842387.png)
- 找到系统环境变量设置
    - ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628092223591.png)
- 设置 Data Execution Prevention 选项页中，选择 Turn on DEP for essential Windows programs and services only
    - ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628092310977.png)
- 重启电脑后即生效

# 3 如何确认DEP已被关闭

- 在CMD下输入以下命令，来判断是否DEP已关闭

```
wmic OS Get DataExecutionPrevention_SupportPolicy
```

- ![](FILES/090ARSim启动时报错提示DEP_Data%20Execution%20Prevention/image-20240628093124522.png)
- 返回数字代表的含义
    - 0 – DEP is disabled for all processes.
    - 1 – DEP is enabled for all processes.
    - **2 – DEP is enabled for only Windows system components and services. (Default)**
        - ⭐期望得到的结果
    - 3 – DEP is enabled for all processes.
- 修改完成后，尝试重新开启Automation Studio软件并启动ARSim，看是否可以正常使用。若仍不能，更新Windows，或者回滚Windows的更新至上一个版本。

# 4 参考链接

- GUID: c7703318-f20a-43ee-ae45-3e5723c96b7c
- [B&R Online Help (br-automation.com)](https://help.br-automation.com/#/en/4/automationruntime%2Ftargets%2Far000%2Fcommissioning%2Fdataexecutionprevention.htm)

# 5 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-06-28 | YZY | 初次创建 |
