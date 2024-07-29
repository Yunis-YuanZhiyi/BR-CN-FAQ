> Tags: #通信 #DTM #FieldbusDevices

- [1 059如何从DTM Manager删除错误导入的Fieldbus Devices](#_1-059%E5%A6%82%E4%BD%95%E4%BB%8Edtm-manager%E5%88%A0%E9%99%A4%E9%94%99%E8%AF%AF%E5%AF%BC%E5%85%A5%E7%9A%84fieldbus-devices)
- [2 导致原因](#_2-%E5%AF%BC%E8%87%B4%E5%8E%9F%E5%9B%A0)
- [3 解决方式](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 059如何从DTM Manager删除错误导入的Fieldbus Devices

- 有时候会遇到无法使用第三方设备管理器删除现场总线设备的情况
- 在第三方设备管理器（3rd‑Party Device Manager）中将 EDS 文件作为“现场总线设备Fieldbus Devices”（不是 DTM）导入后，该设备会显示出来，但无法再删除。
- ![](FILES/059如何从DTM%20Manager删除错误导入的Fieldbus%20Devices/image-20240730000708384.png)

# 2 导致原因

- 现场总线设备存储在 `C:\ProgramData\BR\AS4xx\Hardware\Modules\` 中。
- 此文件夹中每个模块都有一个文件夹。模块文件夹名称以 FBC 开头。
    - xxxx → CANopen 设备 FBE
    - xxxx → Powerlink 设备 FBP
    - xxxx → Profibus 设备 FBD
    - xxxx → DTM 设备
- 文件夹名称的 xxxx 部分由现场总线描述文件的内容自动生成。对于 CANopen EDS 文件，名称由以下参数生成：
    - ![](FILES/059如何从DTM%20Manager删除错误导入的Fieldbus%20Devices/image-20240730000926775.png)
- 此示例指向以下文件夹：
    - ![](FILES/059如何从DTM%20Manager删除错误导入的Fieldbus%20Devices/image-20240730000957595.png)
- 如果 EDS 文件中缺少某些信息，则可能导致 AS 无法识别文件夹名称。在此案例中，缺少 VendorNumber，导致无法在第三方设备管理器中删除设备。

# 3 解决方式

- 要手动删除设备，需要执行以下步骤：
    - 关闭Automation Studio
    - 为避免意外，将“AS4xx”文件夹进行整体备份
    - 从“`AS4xx\Hardware\Modules`”文件夹中删除无效的现场总线设备
    - 在文本编辑器中打开文件“`AS4xx\HardwareModules. xml`”
        - 通过搜索查找设备的元素 `<Module>`
        - 删除无效设备的元素`<Module>`
        - ![](FILES/059如何从DTM%20Manager删除错误导入的Fieldbus%20Devices/image-20240730001231600.png)

# 4 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-07-30 | YZY | 初次创建 |
