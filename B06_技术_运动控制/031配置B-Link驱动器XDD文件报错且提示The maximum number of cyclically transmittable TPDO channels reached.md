> Tags: #B_Link #运动控制

- [1 031配置B-Link驱动器XDD文件报错且提示The maximum number of cyclically transmittable TPDO channels reached](#1%20031%E9%85%8D%E7%BD%AEB-Link%E9%A9%B1%E5%8A%A8%E5%99%A8XDD%E6%96%87%E4%BB%B6%E6%8A%A5%E9%94%99%E4%B8%94%E6%8F%90%E7%A4%BAThe%20maximum%20number%20of%20cyclically%20transmittable%20TPDO%20channels%20reached)
- [2 解决方式](#2%20%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [3 更新日志](#3%20%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 031配置B-Link驱动器XDD文件报错且提示The maximum number of cyclically transmittable TPDO channels reached

- AS报错信息
    - The maximum number of cyclically transmittable TPDO channels reached.(PDOTPDOChannelObjects = 25)
- ![](FILES/031配置B-Link驱动器XDD文件报错且提示The%20maximum%20number%20of%20cyclically%20transmittable%20TPDO%20channels%20reached/image-20240120002823640.png)

# 2 解决方式

- 方式一：修改XDD文件
    - 将XDD文件中的下面两项内容删除
        - ![](FILES/031配置B-Link驱动器XDD文件报错且提示The%20maximum%20number%20of%20cyclically%20transmittable%20TPDO%20channels%20reached/image-20240120003133668.png)
    - 修改一下XDD文件名称
    - 重新导入XDD到AS软件中
- 方式二：升级Automaiton Studio 4.12 的SP包至4.12.5
    - [V4.12 AS Upgrade (4.12.5.95_SP) | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/zh/downloads/software/automation-studio/automation-studio-412/v412-as-upgrade-412595-sp/)

# 3 更新日志

| 日期     | 修改人     | 修改内容     |
|:-----|:-----|:-----|
| 2024-01-18     | ZhouShenyang     | 初次创建     |
