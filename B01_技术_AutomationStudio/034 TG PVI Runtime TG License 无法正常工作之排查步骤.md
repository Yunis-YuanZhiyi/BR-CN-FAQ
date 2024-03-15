> Tags: #TG #PVI
- [1 PVI Runtime TG License 无法正常工作之排查步骤](#1%20PVI%20Runtime%20TG%20License%20%E6%97%A0%E6%B3%95%E6%AD%A3%E5%B8%B8%E5%B7%A5%E4%BD%9C%E4%B9%8B%E6%8E%92%E6%9F%A5%E6%AD%A5%E9%AA%A4)
- [2 问题描述](#2%20%E9%97%AE%E9%A2%98%E6%8F%8F%E8%BF%B0)
- [3 解决方案](#3%20%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
- [4 问题求助资料准备](#4%20%E9%97%AE%E9%A2%98%E6%B1%82%E5%8A%A9%E8%B5%84%E6%96%99%E5%87%86%E5%A4%87)
	- [4.1 发送邮件](#4.1%20%E5%8F%91%E9%80%81%E9%82%AE%E4%BB%B6)

# 1 PVI Runtime TG License 无法正常工作之排查步骤

# 2 问题描述

- 普通台式机插入PVI Runtime TG Dongle后，PVI monitor中security mode无法进入Runtime模式，一直处于Trial模式。
- 版本信息：
- PVI：4.5.3.50；
- Winodws：Windows7 SP1 7601；
- ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615142648.png)
- 可能是PVI Runtime TG License没有被系统正常识别造成。

# 3 解决方案

- 首先通过Technologu Guarding与CodeMeter查看Dongle内是否存在相应License。PVI安装文件内包含Technology Guarding与CodeMeter。如下图：
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615142849.png)
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150706.png)
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150723.png)
- 如果TG识别正常，请卸载原版本PVI，重新安装PVI。安装PVI过程中务必关闭其他不相关软件，并且检查1TG0500.02驱动选项是否勾选，如下图：
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150858.png)
- 正常状态如下：
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150927.png)

# 4 问题求助资料准备

- 如果以上步骤仍然无法解决问题，则需要提供以下文件供总部进行分析：
	- msinfo32 report
	- Eventlogs
	- PviLogs
	- Snapshot
	- CodeMeter Logs
- 文件获取方法：
    - System Information (msinfo32)：
        - 键盘按Win+R > 输入"msinfo32" > OK > File > Save > `*.NFO` > Save；
    - Event Viewer (eventvwr.msc)：
        键盘按Win+R > 输入 "eventvwr.msc" > OK > 选择"Windows Logs" > Application andSystem > Right click > "Save all events as .." > `*.evtx` > Save > Display information for these languages: English (United States) > OK；
- PVI Logs
    - 注：PVI log文件需要使用系统管理员权限运行 PVI monitor。
    - 首先，需要在PVI Diagnostics中设置日志参数，步骤如下：
    - Global Mode: "Log Details"
    - Global Verbose: "True"
    - Global Time Stamp: "Date + Time"
    - ![Img](./FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151154.png)
    - Component: PviMan.exe/System
    - Logging mode: "Log Details"
    - Verbose: "True"
    - File Size (KB): 50000
    - File Name: C:\Temp\Log\PviMan_Sys.log
    - Time Stamp: Date + Time
    - ![Img](./FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151230.png)
    - 配置完成后，必须按"Apply"，并且重启 PVI manager才能进行生效。日志文件会保存在“C:\Temp\Log”路径下。
- Snapshot
    - 在PVI Diagnostics-Path选择Snapshot文件的保存路径，点击“Snapshot”即可。
    - ![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151315.png)
- Codemeter Log
    - Start > Codemeter Command Promt
    - Enter "`cmu32 --cmdust --file C:\Temp\codemeter.log`"

## 4.1 发送邮件

- 最后，将获取到的文件上传，说明情况，发送至 support.cn@br-automation
