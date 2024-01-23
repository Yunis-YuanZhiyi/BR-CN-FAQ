> Tags: #DTM #AS

- [081贝加莱AS软件与Omron Sysmac studio同时安装报错Failed to create device description dictionary](#081%E8%B4%9D%E5%8A%A0%E8%8E%B1AS%E8%BD%AF%E4%BB%B6%E4%B8%8EOmron%20Sysmac%20studio%E5%90%8C%E6%97%B6%E5%AE%89%E8%A3%85%E6%8A%A5%E9%94%99Failed%20to%20create%20device%20description%20dictionary)
- [原因](#%E5%8E%9F%E5%9B%A0)
- [建议解决方式](#%E5%BB%BA%E8%AE%AE%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [更新日志](#%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 081贝加莱AS软件与Omron Sysmac studio同时安装报错Failed to create device description dictionary

- 同时安装贝加莱AS 4.12 与欧姆龙 Sysmac studio V1.56，当运行Automation Studio软件时报错
- ![](FILES/081贝加莱AS软件与Omron%20Sysmac%20studio同时安装报错Failed%20to%20create%20device%20description%20dictionary/image-20240123212119596.png)
- Failed to create device description dictionary. An item with the same key has already been added.
- Could not load DtmDevice Type information from device description file
- 重新安装AS的DTM无效，重装AS软件无效
- 相关版本
    - 贝加莱相关
        - DTM software version V1.6.6.1
    - 欧姆龙软件
        - Sysmac studio version V1.56
        - ![](FILES/081贝加莱AS软件与Omron%20Sysmac%20studio同时安装报错Failed%20to%20create%20device%20description%20dictionary/image-20240123212427844.png)

# 原因

- 欧姆龙软件也使用DTM相关的软件，与贝加莱软件的DTM冲突
- 只能安装一个版本的贝加莱DTM，一台 PC 上不可能有多个版本。
- 例如
    - SYCON.net 与 Hilscher DTM 库不兼容，Hilscher DTM 库和 SYCON.net 不能并行安装在一台 PC 上。
        - Hilscher DTM库是贝加莱DTM的一部分，由Automation Studio隐式安装。该库是在Automation Studio中使用FDT/DTM和netX的基础。
        - SYCON.net 是配置和诊断软件，包含 Hilscher DTM 库的一部分，是 Hilscher 其他产品所必需的。
- 贝加莱在线帮助相关说明
    - [B&R Online Help (br-automation.com)](https://help.br-automation.com/#/en/6/communication%2Ffieldbuses%2Fnetx%2Fnetx_limitations.html)

# 建议解决方式

- 方式一:
    - 在同一台电脑上，仅安装欧姆龙开发软件或贝加莱开发软件，卸载另一个软件
    - 例如
        - 卸载贝加莱 AS 与 B+R DTM 软件
        - 卸载欧姆龙 OMRON 软件
        - 确认所有的 DTM 软件都被卸载了
        - 重新安装 AS 软件与 B+R DTM Library
- 方式二：
    - 将贝加莱AS开发软件安装在虚拟机（VMWare，VirtualBox）中使用

# 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2024-01-23     | YuanZhiyi<br>HuangHaoran     | 初次创建     |
