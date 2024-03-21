> Tags: #AS #程序更新 #Hypervisor

# B01.088-在线更新程序报错LOG CANNOT EXECUTE COMMAND

- 使用 Automation Studio更新程序，无法更新成功，提示如下
    - `\LOG CANNOT EXECUTE COMMAND: Object reference not set to an instance of an object.`
    - ![](FILES/088在线更新程序报错LOG%20CANNOT%20EXECUTE%20COMMAND/image-20240321133927868.png)
- 使用相关技术与版本
    - 使用了Hyperviosr技术
    - AR F4.93
    - 硬件为APC910-TS17.04

# 原因与解决方式

- AR配置中参数：Module system on target → Minimum user partition size，原配置为0，被修改为其他数值后在线更新即会报此错误。将此参数改回原本参数0即解决问题。
- ![](FILES/088在线更新程序报错LOG%20CANNOT%20EXECUTE%20COMMAND/image-20240321134317002.png)

# 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-03-21 | HHR<br>YZY | 初次创建 |
