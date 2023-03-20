# [TG] PVI Runtime TG License 无法正常工作之排查步骤
## 问题描述
普通台式机插入PVI Runtime TG Dongle后，PVI monitor中security mode无法进入Runtime模式，一直处于Trial模式。
版本信息：
PVI：4.5.3.50；
Winodws：Windows7 SP1 7601；

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615142648.png)

可能是PVI Runtime TG License没有被系统正常识别造成。
## 解决方案
- 首先通过Technologu Guarding与CodeMeter查看Dongle内是否存在相应License。PVI安装文件内包含Technology Guarding与CodeMeter。如下图：

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615142849.png)

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150706.png)

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150723.png)

-  如果TG识别正常，请卸载原版本PVI，重新安装PVI。安装PVI过程中务必关闭其他不相关软件，并且检查1TG0500.02驱动选项是否勾选，如下图：

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150858.png)

- 正常状态如下：

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615150927.png)

如果以上步骤仍然无法解决问题，则需要提供以下文件供总部进行分析：


	1. msinfo32 report
	2. Eventlogs
	3. PviLogs
	4. Snapshot
	5. CodeMeter Logs

文件获取方法：
System Information (msinfo32)：
    键盘按Win+R > 输入"msinfo32" > OK > File > Save > *.NFO > Save；
Event Viewer (eventvwr.msc)：
    键盘按Win+R  >输入 "eventvwr.msc" > OK > 选择"Windows Logs" > Application andSystem > Right click > "Save all events as .." > *.evtx > Save > Display information for these languages: English (United States) > OK；

PVI Logs

    注：PVI log文件需要使用系统管理员权限运行 PVI monitor。

    首先，需要在PVI  Diagnostics中设置日志参数，步骤如下：
    Global Mode: "Log Details"
    Global Verbose: "True"
    Global Time Stamp: "Date + Time"

    ![Img](./FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151154.png)

    Component: PviMan.exe/System
    Logging mode: "Log Details"
    Verbose: "True"
    File Size (KB): 50000
    File Name: C:\Temp\Log\PviMan_Sys.log
    Time Stamp: Date + Time

    ![Img](./FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151230.png)

  配置完成后，必须按"Apply"，并且重启 PVI manager才能进行生效。日志文件会保存在“C:\Temp\Log”路径下。

Snapshot

在PVI  Diagnostics-Path选择Snapshot文件的保存路径，点击“Snapshot”即可。

![Img](FILES/030[TG]%20PVI%20Runtime%20TG%20License%20无法正常工作之排查步骤.md/img-20220615151315.png)

Codemeter Log
- Start > Codemeter Command Promt
- Enter "cmu32 --cmdust --file C:\Temp\codemeter.log"



最后，将获取到的文件上传至CSP附件，或发送 Support.cn@br-automation。