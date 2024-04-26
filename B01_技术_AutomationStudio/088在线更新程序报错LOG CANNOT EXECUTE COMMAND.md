> Tags: #AS #程序更新 #Hypervisor

- [1 B01.088-在线更新程序报错LOG CANNOT EXECUTE COMMAND](#_1-b01088-%E5%9C%A8%E7%BA%BF%E6%9B%B4%E6%96%B0%E7%A8%8B%E5%BA%8F%E6%8A%A5%E9%94%99log-cannot-execute-command)
- [2 现象一：在线更新报错](#_2-%E7%8E%B0%E8%B1%A1%E4%B8%80%EF%BC%9A%E5%9C%A8%E7%BA%BF%E6%9B%B4%E6%96%B0%E6%8A%A5%E9%94%99)
	- [2.1 原因与解决方式](#_21-%E5%8E%9F%E5%9B%A0%E4%B8%8E%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [3 现象二：离线烧卡报错](#_3-%E7%8E%B0%E8%B1%A1%E4%BA%8C%EF%BC%9A%E7%A6%BB%E7%BA%BF%E7%83%A7%E5%8D%A1%E6%8A%A5%E9%94%99)
	- [3.1 解决方式](#_31-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B01.088-在线更新程序报错LOG CANNOT EXECUTE COMMAND

# 2 现象一：在线更新报错

- 使用 Automation Studio更新程序，无法更新成功，提示如下
    - `\LOG CANNOT EXECUTE COMMAND: Object reference not set to an instance of an object.`
    - ![](FILES/088在线更新程序报错LOG%20CANNOT%20EXECUTE%20COMMAND/image-20240321133927868.png)
- 使用相关技术与版本
    - 使用了Hyperviosr技术
    - AR F4.93
    - 硬件为APC910-TS17.04

## 2.1 原因与解决方式

- AR配置中参数：Module system on target → Minimum user partition size，原配置为0，被修改为其他数值后在线更新即会报此错误。将此参数改回原本参数0即解决问题。
- ![](FILES/088在线更新程序报错LOG%20CANNOT%20EXECUTE%20COMMAND/image-20240321134317002.png)

# 3 现象二：离线烧卡报错

- 使用烧卡方式，发现提示报错，提示内容为
- `\LOG CANNOT_EXECUTE_COMMAND: External component has thrown an exception.`
- ![](FILES/088在线更新程序报错LOG%20CANNOT%20EXECUTE%20COMMAND/image-20240427003352844.png)
- 使用版本
    - AS4.10.6.39 SP
    - AR G4.91

## 3.1 解决方式

- Automation Studio软件重启后解决

# 4 更新日志

| 日期         | 修改人        | 修改内容             |
| :--------- | :--------- | :--------------- |
| 2024-03-21 | HHR<br>YZY | 初次创建             |
| 2024-04-27 | WYS        | 补充更新离线方式烧卡报错处理方式 |
