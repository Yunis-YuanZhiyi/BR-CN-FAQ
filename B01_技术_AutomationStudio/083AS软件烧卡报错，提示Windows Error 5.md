> Tags: #RUC #烧卡

- [1 083AS软件烧卡报错，提示Windows Error #5](#1%20083AS%E8%BD%AF%E4%BB%B6%E7%83%A7%E5%8D%A1%E6%8A%A5%E9%94%99%EF%BC%8C%E6%8F%90%E7%A4%BAWindows%20Error%20#5)
- [2 报错原因](#2%20%E6%8A%A5%E9%94%99%E5%8E%9F%E5%9B%A0)
- [3 解决方式一：重复多试几次](#3%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E9%87%8D%E5%A4%8D%E5%A4%9A%E8%AF%95%E5%87%A0%E6%AC%A1)
- [4 解决方式二：更换一张合适的卡](#4%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%BA%8C%EF%BC%9A%E6%9B%B4%E6%8D%A2%E4%B8%80%E5%BC%A0%E5%90%88%E9%80%82%E7%9A%84%E5%8D%A1)
- [5 解决方式三：使用管理员权限操作软件、关闭杀毒软件、重启电脑](#5%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%89%EF%BC%9A%E4%BD%BF%E7%94%A8%E7%AE%A1%E7%90%86%E5%91%98%E6%9D%83%E9%99%90%E6%93%8D%E4%BD%9C%E8%BD%AF%E4%BB%B6%E3%80%81%E5%85%B3%E9%97%AD%E6%9D%80%E6%AF%92%E8%BD%AF%E4%BB%B6%E3%80%81%E9%87%8D%E5%90%AF%E7%94%B5%E8%84%91)
- [6 解决方式四：安装高版本PVI软件](#6%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E5%9B%9B%EF%BC%9A%E5%AE%89%E8%A3%85%E9%AB%98%E7%89%88%E6%9C%ACPVI%E8%BD%AF%E4%BB%B6)
- [7 更新日志](#7%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B01.083-AS软件烧卡报错，提示Windows Error #5

- 使用Automation Studio软件进行烧卡操作，当必须更改分区大小时，会出现消息框“Windows Error #5 ”。
- ![](FILES/083AS软件烧卡报错，提示Windows%20Error%205/image-20240224211312016.png)
- 报错内容为：
    - Removable storage device F:\ cannot be created. Windows error #5 occured.

# 2 报错原因

- Windows error #5 意味着无法访问硬盘设备（CF卡，CFast卡）。
- 如果其他的Windows任务正在占用着CFast卡并阻止PVI软件访问，则会提示出类似的报错。
- 当使用Windows 10 1809及以上版本，也可能会出现类似问题

# 3 解决方式一：重复多试几次

- 重复烧卡步骤。
- 第二次执行相同步骤时可能就不会出现此错误。

# 4 解决方式二：更换一张合适的卡

- 可能原先使用的卡有问题。
- 换用一张CFast/CF卡
    - 之前使用32GB/128GB的CFast卡报错，换用2GB的CFast卡后则正常。

# 5 解决方式三：使用管理员权限操作软件、关闭杀毒软件、重启电脑

# 6 解决方式四：安装高版本PVI软件

- 如果使用Windows 10 1809及以上版本，即便没有其他任务占用，也可能出现Windows error #5 报错。
- 重新安装使用比PVI 4.6.03 与 PVI 4.7.02更高的PVI版本。

# 7 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2024-02-24 | YZY | 初次创建 |
