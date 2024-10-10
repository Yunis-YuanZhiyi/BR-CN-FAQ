> Tags: #C70

- [1 054将C70设置为VNC Client (Terminal模式)](#_1-054%E5%B0%86c70%E8%AE%BE%E7%BD%AE%E4%B8%BAvnc-client-terminal%E6%A8%A1%E5%BC%8F)
- [2 解决方式（AS4.3）](#_2-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%EF%BC%88as43%EF%BC%89)
	- [2.1 STEP 1 建立工程](#_21-step-1-%E5%BB%BA%E7%AB%8B%E5%B7%A5%E7%A8%8B)
	- [2.2 STEP 2 以太网添加终端](#_22-step-2-%E4%BB%A5%E5%A4%AA%E7%BD%91%E6%B7%BB%E5%8A%A0%E7%BB%88%E7%AB%AF)
	- [2.3 STEP 3 配置 PPC7X](#_23-step-3-%E9%85%8D%E7%BD%AE-ppc7x)
	- [2.4 STEP 4 制作 USB 更新盘](#_24-step-4-%E5%88%B6%E4%BD%9C-usb-%E6%9B%B4%E6%96%B0%E7%9B%98)
	- [2.5 STEP 5 USB 更新 C70](#_25-step-5-usb-%E6%9B%B4%E6%96%B0-c70)
	- [2.6 BOOT 模式不响应 USB](#_26-boot-%E6%A8%A1%E5%BC%8F%E4%B8%8D%E5%93%8D%E5%BA%94-usb)
- [3 在AS4.12中将C70设置为Terminal模式](#_3-%E5%9C%A8as412%E4%B8%AD%E5%B0%86c70%E8%AE%BE%E7%BD%AE%E4%B8%BAterminal%E6%A8%A1%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 054将C70设置为VNC Client (Terminal模式)

- 🔴注意：C30与C70仅支持VC4方案画面显示，不支持mappView方案画面显示。
    - [041产品介绍_PowerPanel系列](041产品介绍_PowerPanel系列.md)
- C70 系列的屏，想作为 VNC Client 来使用，访问 PPC2100 作为主控 制器里面运行的画面。这种功能称为终端模式 Terminal Mode，一般由 T 系列的屏来做。
- 这个文档用来介绍在特殊需求下，如何将 PPC70 系列的屏配置为终端模式。

# 2 解决方式（AS4.3）

- AS 环境，使用了 4.3.5.113 版本，在 4.2 版本中试过也是可行的

## 2.1 STEP 1 建立工程

- 首先在 AS 里建立一个工程，硬件结构要和实际设备一样，这里使用的是 APC2100 作为项目的主控制器。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010134907211.png)
- 要为添加 C70 的 ETH 口分配一个静态 IP 地址。

## 2.2 STEP 2 以太网添加终端

- 在需要连接的 ETH 网口，选择 Add Hardware Module，这里两个网口不能混用，选择在哪个网口下添加终 端，后续实际连接的时候也只能连在那个网口下。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010134940779.png)

## 2.3 STEP 3 配置 PPC7X

- 右击并打开 4PPC7X 的配置
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135010067.png)
- 设置说明：
    - INA node number
        - 进入 Terminal Mode 以后会作为节点号，注意不要和相连接的主控制器的 ETH 口设置一样的 INA 号码。
    - Ethernet parameters
        - 给 4PPC7X 设置一个静态 IP 地址，与掩码匹配让这个 IP 地址和主控制器的 ETH 口处于同一个子网中。
    - VC Mapping
        - 这里主要要配置的 VC object name，也就是这个终端要用来显示主控制器（2100）上的哪个 Visualization 画 面，从项目里选择一个与之对应。
        - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135042428.png)

## 2.4 STEP 4 制作 USB 更新盘

- 在 AS4.3 中，点击 Project → Project Installation → Generate Project Installation Package
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135111946.png)
- 这里要选择对型号，这里是对 4PPC70 进行 USB 盘制作，选择第二项，点击 OK
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135140164.png)
- 这里的各个设置推荐和图片中一样
- <span style="background:#A0CCF6">使用单分区硬盘</span>
- Target Identification 为 via host name，host name 填写 vxTarget，因为后面会进入出厂设置来进行 USB 更新
- 制作完成后，确认 U 盘有如下内容：
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135158577.png)

## 2.5 STEP 5 USB 更新 C70

- 最后一步是用制作好的 USB 盘去更新 C70，但是 C70 的 AR Runtime 存在一些问题，所以我们要进到 BOOT 模式来更新，这个在最后附上说明。
- **STEP 1 正常启动 C70**
    - 首先我们将 USB 插入 C70 的接口，启动 C70，这时 C70 里如果有程序，那么这个程序就会正常启动，不会 响应 USB 盘中的更新内容。当然也存在可能，直接就更新了，那就直接完成了更新。
- **STEP 2 进入 BOOT 模式**
    - 如果 C70 还是运行原先的程序的话，我们保持 USB 盘插在 C70 上，找到背部的 RESET 按键，轻按一下（小 于 2 秒）然后放开，C70 会黑屏重启，这时再按住 RESET（大于 2 秒），C70 会再次重启，（小黑点，白 屏）然后会进入 BOOT 模式。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135223585.png)
- **STEP 3 C70 读取 USB**
    - 在 BOOT 模式中 C70 会读取 USB 中的内容，此时等待 30 秒左右 C70 会开始重启，并反复 2 到 3 次，然后就 能完成更新，启动后自动进入 Terminal 模式
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135243807.png)
    - 进入 Terminal 模式后，将网线连接至工程中 PLC 的以太网口，C70 就会自动找到 Terminal Server 了，并显示主控制器上运行的 VC 内容。至此完成 C70 配置到 Terminal Mode 使用的全部过程。

## 2.6 BOOT 模式不响应 USB

- 在第一次进入 BOOT 模式后，且 USB 已插入，但是 C70 仍然不更新（等待超过 1 分钟也无任何反应，停留在 BOOT 模式），那么可能是 C70 的硬盘中有一些错误内容导致无法正常加载更新程序。
- 这时首先要确认这个 USB 盘是支持 B&R 设备更新（更新过其他 PLC）
    - 如果不能正常使用，可以考虑查看 [021 C70、CP04XX、CP13XX 无法启动的恢复方法](../B03_技术_诊断/021%20C70、CP04XX、CP13XX%20无法启动的恢复方法.md) 按照步骤操作。
- 如果确认该 USB 可用且里面的内容是正确按照上面制作的，那么将电脑网口与 C70 相连接，将电脑网口改为和 C70 的网口属于同一网段。在 AS 中搜索找到 C70，发现所有参数均为 0。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135313459.png)
- 通过 Set IP Parameters 来修改 C70 的参数，将 IP 和掩码调整到与电脑同一网段，然后连接上 C70。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135330602.png)
- 可以看到处于 BOOT 模式的 C70
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135351052.png)
- 这时需要通过 AS 对 C70 的硬盘进行格式化，去除错误内容
- 在菜单中打开 Online->Services->HDD / CF Utility（在 C70 正常模式下该功能为禁用）
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135405117.png)
- 如果硬盘有 3 个分区，CDE 的，点击 Edit Partitions，将分区设置为 1 个，命名 SYSTEM。如果只有 1 个分区 SYSTEM，点击 Format。
    - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010135416999.png)
- 等待硬盘格式化后，保持 USB 插入，断电重启再进入 BOOT 模式即可，进入 BOOT 模式后 C70 会读取 USB 内容，如同 `STEP 5 USB更新 C70` 中完成更新。

# 3 在AS4.12中将C70设置为Terminal模式

- 创建一个Terminal 项目，详细步骤参考 AS在线帮助 [Terminal project development](https://help.br-automation.com/#/en/4/visualization%2Fvcremote%2Fterminal%2Fterminalmode_projectmanagement.htm)
- 对VNC Server项目设备进行程序（离线安装或在线传输）
- 在AS中创建一个 USB installation Stick
    - 菜单栏中 Project → Project Installation → Generate Project Installation Package
        - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010151545379.png)
        - 必须选择 “Normal B&R module system (1 partition)” 作为 B&R module system，否则安装不会起作用
        - ![](FILES/054将C70设置为VNC%20Client%20(Terminal模式)/image-20241010151726736.png)
- 将U盘插入C70面板并将其置于BOOT模式
    - 找到背部的 RESET 按键，轻按一下（小 于 2 秒）然后放开，C70 会黑屏重启，这时再按住 RESET（大于 2 秒），C70 会再次重启，（小黑点，白屏）然后会进入 BOOT 模式。
- 来源
    - [Terminal mode with C70 in AS 4.12](https://community.br-automation.com/t/terminal-mode-with-c70-in-as-4-12/701)

# 4 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2018-08-03 | WYQ | 初次创建 |
| 2024-10-10 | YZY | 更新文档 |
