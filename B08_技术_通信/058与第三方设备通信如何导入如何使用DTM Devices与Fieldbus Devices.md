> Tags: #通信

- [1 B08.058.与第三方设备通信如何导入如何使用DTM Devices与Fieldbus Devices](#_1-b08058%E4%B8%8E%E7%AC%AC%E4%B8%89%E6%96%B9%E8%AE%BE%E5%A4%87%E9%80%9A%E4%BF%A1%E5%A6%82%E4%BD%95%E5%AF%BC%E5%85%A5%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8dtm-devices%E4%B8%8Efieldbus-devices)
- [2 3rd‑Party Device Manager第三方设备管理器](#_2-3rd%E2%80%91party%C2%A0device%C2%A0manager%E7%AC%AC%E4%B8%89%E6%96%B9%E8%AE%BE%E5%A4%87%E7%AE%A1%E7%90%86%E5%99%A8)
- [3 导入从站模块](#_3-%E5%AF%BC%E5%85%A5%E4%BB%8E%E7%AB%99%E6%A8%A1%E5%9D%97)
- [4 关联相关DTM使用文档](#_4-%E5%85%B3%E8%81%94%E7%9B%B8%E5%85%B3dtm%E4%BD%BF%E7%94%A8%E6%96%87%E6%A1%A3)
- [5 DTM配置注意事项](#_5-dtm%E9%85%8D%E7%BD%AE%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B08.058.与第三方设备通信如何导入如何使用DTM Devices与Fieldbus Devices

- Automation Studio中支持第三方设备，因此Automation Runtime也以两种不同的方式支持：
    - 通过netx使用FDT/DTM技术
    - 通过设备描述文件进行配置
- 第三方设备无缝地集成到Automation Studio中。安装后，它们可以像任何其他设备一样在Automation Studio中使用。这意味着这些设备可以在物理视图、系统设计器和相应的配置编辑器中使用，并且可以插入，在项目中配置和删除。
- 管理第三方设备在第三方设备管理器对话框中完成。使用此对话框，可以导入设备描述文件，作为DTM或常规现场总线设备。此外，可以删除或导出导入的设备。

# 2 3rd‑Party Device Manager第三方设备管理器

- 为了简化对其他制造商设备的管理，Automation Studio 使用了第三方设备管理器。对话框会显示 Automation Studio 中所有可用的第三方设备列表，这些设备也可在此使用。
- 第三方设备管理器通过菜单选项 "工具"/"管理第三方设备 "启动。
- ![](FILES/058与第三方设备通信如何导入如何使用DTM%20Devices与Fieldbus%20Devices/image-20240729225616464.png)
- 如果目录未更新（Update DTM Catalog），则无法在Physical View中插入或配置设备。
- 如果手动导入多个设备描述文件，则只需在导入最后一个文件后执行一次更新。
- ⭐ 导入的 <span style="background:#A0CCF6">DTM Devices</span> 文件实际均存储在 `C:\ProgramData\SYCONnet` 文件夹下（ProgramData文件夹为隐藏文件夹）
    - ![](FILES/058与第三方设备通信如何导入如何使用DTM%20Devices与Fieldbus%20Devices/image-20240729233841951.png)
    - 可以直接把配置文件直接拷贝在对应文件夹下，再点击Update DTM Catalog
- 导入的 <span style="background:#A0CCF6">Fieldbus Devices</span> 文件存储在 `C:\ProgramData\BR\AS412\Hardware\Modules` 文件夹
    - ![](FILES/058与第三方设备通信如何导入如何使用DTM%20Devices与Fieldbus%20Devices/image-20240729235933145.png)

# 3 导入从站模块

- 在贝加莱通信主站模块下的（DTM），右键 → Add Hardware Module → 选择需要导入的从站
- ![](FILES/058与第三方设备通信如何导入如何使用DTM%20Devices与Fieldbus%20Devices/image-20240729233435762.png)
- 右键从站模块，点击Device Configuration，可对模块进行配置，也查看文件的存放位置。
- ![](FILES/058与第三方设备通信如何导入如何使用DTM%20Devices与Fieldbus%20Devices/image-20240729233649417.png)

# 4 关联相关DTM使用文档

- [060可以编译通过但无法配置其他人电脑中正常的DTM模块从站](../B01_技术_AutomationStudio/060可以编译通过但无法配置其他人电脑中正常的DTM模块从站.md)
- [059AS中插入X20IF1043-1模块后编译报错](../B01_技术_AutomationStudio/059AS中插入X20IF1043-1模块后编译报错.md)
- [059如何从DTM Manager删除错误导入的Fieldbus Devices](059如何从DTM%20Manager删除错误导入的Fieldbus%20Devices.md)

# 5 DTM配置注意事项

- 第三方设备的从站文件（GSD文件，EDS文件）均存储在 `C:\ProgramData\SYCONnet` 文件夹下
- 贝加莱提供的硬件模块（例如X20IF1043-1）所对应的EDS文件存储在 `C:\Program Files (x86)\Hilscher GmbH\DTM Library\CANopenSlaveDTM\EDS` 文件夹下
- DTM版本使用需要注意版本，不同的DTM版本所生成的项目配置会有所不同，项目迁移时，建议确认DTM版本一致。
    - ![image-20240724230302360](../B01_技术_AutomationStudio/FILES/059AS中插入X20IF1043-1模块后编译报错/image-20240724230302360.png)
- 若DTM使用出现异常问题，建议
    - 卸载 B+R DTM（建议使用Geek Unistaller软件进行卸载）
    - 下载最新的AS软件SP更新包（AS软件更新至最新版本，AS4.12.5 SP）
    - 下载并安装最新的B+R DTM（直接在官网搜索B&R DTM）
        - 若提示冲突，查看 [012AS安装软件提示当前安装版本低于已安装版本](../C02_AS软件注册与安装问题/012AS安装软件提示当前安装版本低于已安装版本.md)

# 6 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-07-29 | YZY | 初次创建 |
