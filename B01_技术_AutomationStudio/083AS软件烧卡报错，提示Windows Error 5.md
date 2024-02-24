> Tags: #RUC #烧卡

# 083AS软件烧卡报错，提示Windows Error #5

- 使用Automation Studio软件进行烧卡操作，当必须更改分区大小时，会出现消息框“Windows Error #5 ”。
- ![](FILES/083AS软件烧卡报错，提示Windows%20Error%205/image-20240224211312016.png)
- 报错内容为：
    - Removable storage device F:\ cannot be created. Windows error #5 occured.

# 报错原因

- Windows error #5 意味着无法访问硬盘设备（CF卡，CFast卡）。
- 如果其他的Windows任务正在占用着CFast卡并阻止PVI软件访问，则会提示出类似的报错。
- 当使用Windows 10 1809及以上版本，也可能会出现类似问题

# 解决方式一：重复多试几次

- 重复烧卡步骤。
- 第二次执行相同步骤时可能就不会出现此错误。

# 解决方式二：更换一张合适的卡

- 可能原先使用的卡有问题。
- 换用一张CFast/CF卡
    - 之前使用32GB/128GB的CFast卡报错，换用2GB的CFast卡后则正常。

# 解决方式三：使用管理员权限操作软件、关闭杀毒软件、重启电脑

# 解决方式四：安装高版本PVI软件

- 如果使用Windows 10 1809及以上版本，即便没有其他任务占用，也可能出现Windows error #5 报错。
- 重新安装使用比PVI 4.6.03 与 PVI 4.7.02更高的PVI版本。

# 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2024-02-24     | YuanZhiyi     | 初次创建     |
