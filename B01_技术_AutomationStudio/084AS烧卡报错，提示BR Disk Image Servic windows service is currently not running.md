> Tags: #PVI #烧卡 #RUC

- [1 084AS烧卡报错，提示BR Disk Image Servic windows service is currently not running](#1%20084AS%E7%83%A7%E5%8D%A1%E6%8A%A5%E9%94%99%EF%BC%8C%E6%8F%90%E7%A4%BABR%20Disk%20Image%20Servic%20windows%20service%20is%20currently%20not%20running)
- [2 解决方案](#2%20%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
- [3 更新日志](#3%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 084AS烧卡报错，提示B&R Disk Image Service windows service is currently not running

- 烧卡时报错，详细信息如下：
- Removable storage device cannot be created. The Windows service that is needed to create disks is not started on this system. The required windows service is currently not running. Please start 'B&R Disk Image Service' manually and try it again.
- ![](FILES/084AS烧卡报错，提示BR%20Disk%20Image%20Servic%20windows%20service%20is%20currently%20not%20running/image-20240224213526685.png)

# 2 解决方案

- 1） 安装最新的 PVI。以管理员身份安装。安装过程中关闭防病毒软件。
- 2） 如果重新安装没有帮助，那么：
    - 1. 以管理员身份打开CMD命令提示符（右键单击 -> 以管理员身份运行）
    - 2. 输入命令 `net stop "B&R Disk Image"`（停止正在运行的服务）
            - ![](FILES/084AS烧卡报错，提示BR%20Disk%20Image%20Servic%20windows%20service%20is%20currently%20not%20running/image-20240224214106288.png)
    - 3. 键入命令 `cd C:\BrAutomation\PVI\V4.10\PVI\Tools\PVITransfer`（将位置更改为 PVITransfer 版本 4.10，如果您有其他版本的 PVI，请输入您的版本）
    - 4. 输入 `BrDiskImageSvc.exe /deinstall`（卸载服务）
    - 5. 输入 `BrDiskImageSvc.exe /install /manualstart`（它将重新安装该服务，并应启动它，但我遇到过服务无法启动的问题，因此请继续第 6 步）
    - 6. 打开文件资源管理器（任意文件夹），在路径顶部输入路径 `C:\BrAutomation\PVI\V4.10\PVI\Tools\PVITransfer`，然后双击 BrDiskImageSvc.exe （如果你的 PVI 版本不同，请输入你的版本）
        - ![](FILES/084AS烧卡报错，提示BR%20Disk%20Image%20Servic%20windows%20service%20is%20currently%20not%20running/image-20240224214129507.png)

# 3 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2024-02-24     | YuanZhiyi     | 初次创建     |
