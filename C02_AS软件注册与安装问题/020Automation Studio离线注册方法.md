> Tags: #AS #授权

> 来源：贝加莱官网链接：[Automation Studio离线授权 | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/zh/service/automation-studio-offline-licensing/)

- [1 C02.020-Automation Studio离线注册方法](#_1-c02020-automation-studio%E7%A6%BB%E7%BA%BF%E6%B3%A8%E5%86%8C%E6%96%B9%E6%B3%95)
- [2 简介](#_2-%E7%AE%80%E4%BB%8B)
- [3 STEP A: 在装有 Automation Studio 的 PC 上](#_3-step-a-%E5%9C%A8%E8%A3%85%E6%9C%89-automation-studio-%E7%9A%84-pc-%E4%B8%8A)
- [4 STEP B: 在可以访问网络的 PC 上](#_4-step-b-%E5%9C%A8%E5%8F%AF%E4%BB%A5%E8%AE%BF%E9%97%AE%E7%BD%91%E7%BB%9C%E7%9A%84-pc-%E4%B8%8A)
- [5 STEP C:在装有 Automation Studio 的 PC 上](#_5-step-c%E5%9C%A8%E8%A3%85%E6%9C%89-automation-studio-%E7%9A%84-pc-%E4%B8%8A)

# 1 C02.020-Automation Studio离线注册方法

# 2 简介

- Automation Studio 通常通过 Internet 自动获得许可。
    - [002如何获取Automation Studio的试用注册码](/B01_技术_AutomationStudio/002如何获取Automation%20Studio的试用注册码.md)
- 如果安装 Automation Studio 的 PC 未连接到以太网Internet，则可以使用具有以太网Internet 连接的第二台 PC 进行许可。
- 若贝加莱AS软件授权服务激活失效，提示报错，也可使用此方式进行离线注册激活AS软件
- 为此，请完成以下步骤：

# 3 STEP A: 在装有 Automation Studio 的 PC 上

- <span style="background:#F0A7D8">1___</span>将此文件下载，然后将其复制到 Automation Studio 应获得许可的离线 PC 上。
    - 文件链接：
        - [点击直接下载](/C02_AS软件注册与安装问题/FILES/020Automation%20Studio离线注册方法/br_lif.wbb ':ignore')
        - [备用链接：.wbb 文件通过链接下载](https://technology-guarding.br-automation.com/as-licensing/br_lif.wbb)
- <span style="background:#F0A7D8">2___</span>将wbb文件复制到离线PC上，双击。
    - 或者：通过打开 Windows 开始菜单打开 Code Meter，输入“CodeMeter”，按 Enter 确认并通过拖放导入 .wbb 文件
    - ![](FILES/020Automation%20Studio离线注册方法/image-20230316152502932.png)
- <span style="background:#F0A7D8">3___</span>接受问题 “是否要导入许可证文件” 并选择是
    - ![](FILES/020Automation%20Studio离线注册方法/image-20230316152532376.png)
- <span style="background:#F0A7D8">4___</span>选择出现在窗口左侧的许可证容器（“CmContainer”）,如下图。
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315230455359.png)
- <span style="background:#F0A7D8">5___</span>要创建请求文件，请在下一个出现的窗口中单击“激活许可证”和“下一步”
- <span style="background:#F0A7D8">6___</span>现在选择“创建许可请求”并单击下一步
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315231119915.png)
- <span style="background:#F0A7D8">7.) </span>选择文件保存位置，然后按“提交 Commit”。
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315231540699.png)
- <span style="background:#F0A7D8">8.) </span>将文件传输到可以访问 Internet 的 PC（例如，将其保存到 USB 闪存驱动器或类似设备）

# 4 STEP B: 在可以访问网络的 PC 上

> 也可以是在装有AS的需要授权的同一台电脑，需能够访问网络

- <span style="background:#A0CCF6">9___</span>在底部的字段中输入许可证密钥（试用版本就是注册后邮箱收到的 Key），然后按发送
    - https://www.br-automation.com/en/service/automation-studio-offline-licensing/
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315231931365.png)
- <span style="background:#A0CCF6">10___</span>选择之前保存的 .WibuCmRaC 文件，并点击 Send Request
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315232023571.png)
- <span style="background:#A0CCF6">11___</span>.WibuCmRaU 文件的下载应该会自动开始。
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315232106522.png)
- <span style="background:#A0CCF6">12___</span>将这个更新的 .WibuCmRaU 文件传输到离线 PC（例如使用 USB 闪存驱动器或等效设备）。

# 5 STEP C:在装有 Automation Studio 的 PC 上

- <span style="background:#F0A7D8">13___</span>在 Windows中双击 .WibuCmRaU 进行授权更新。
    - (有当上述方法不起作用时，您可以将文件拖放到“Codemeter”程序中)
- <span style="background:#F0A7D8">14___</span>Automation Studio 现已成功获得许可。
    - ![](FILES/020Automation%20Studio离线注册方法/image-20240315232205716.png)
