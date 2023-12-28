> 020安全CPU No Execution所有模块红灯闪烁两下

> Tags: #安全链 #X20SLXx1x

- [1 使用版本](#1%20%E4%BD%BF%E7%94%A8%E7%89%88%E6%9C%AC)
- [2 现象](#2%20%E7%8E%B0%E8%B1%A1)
- [3 原因](#3%20%E5%8E%9F%E5%9B%A0)
- [4 解决方式](#4%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [5 更新日志](#5%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 使用版本

- Safety Release 1.10
- SafeDESIGNER 4.4.1.0
- 使用CPU模块为X20SLX410

# 2 现象

- 安全程序下载后，安全模块通过Remote Control拨码确认后，安全PLC始终不执行。
    - ![](FILES/020安全CPU%20No%20Execution所有模块红灯闪烁两下/image-20231228225049821.png)
- 所有安全模块的SE 每次闪2次
- ![](FILES/020安全CPU%20No%20Execution所有模块红灯闪烁两下/image-20231228225106931.png)
- ![](FILES/020安全CPU%20No%20Execution所有模块红灯闪烁两下/image-20231228225138893.png)

# 3 原因

- 在安全链程序中X20SLX410的配置参数，Default safe data duration，被错误的改小了，改成了20000。

# 4 解决方式

- 打开SafeDESIGNER软件，将X20SLX410的配置参数，Default safe data duration，改回了150000。
- 重新更新下载安全链程序即解决。

# 5 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2023-12-28     | YuanZhiyi     | 初次创建     |
