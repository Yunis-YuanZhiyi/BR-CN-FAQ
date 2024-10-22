> Tags: #ACOPOS_6D #故障诊断

- [A06.005-ACOPOS 6D常见报错处理](#_a06005-acopos-6d%E5%B8%B8%E8%A7%81%E6%8A%A5%E9%94%99%E5%A4%84%E7%90%86)
- [mapp6D](#_mapp6d)
	- [-1065801966，-1065795583](#_-1065801966%EF%BC%8C-1065795583)
- [Flyway Update](#_flyway-update)
	- [Flyway AD update failed to start with error code: 4](#_flyway-ad-update-failed-to-start-with-error-code-4)
- [更新日志](#_%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# A06.005-ACOPOS 6D常见报错处理

# mapp6D

## -1065801966，-1065795583

- **版本**
    - mapp 1.10
- **现象**
    - 上电logger里面就有 invalid config file报错，但pmc里运行一切正常
    - Logger中记录了 -1065795583 Invalid config file
    - 调用MoveInPlane功能块，报出-1065801966 报错
    - AsmGetshuttle功能块调用，Shuttle.controlif为0
        - ![](FILES/005ACOPOS%206D常见报错处理/image-20240515230847600.png)
- **原因**
    - 实际硬件的定子数量与布局，与mapp 6D配置文件中的Maximum count不一致
    - ![](FILES/005ACOPOS%206D常见报错处理/image-20240515230504734.png)

# Flyway Update

## Flyway AD update failed to start with error code: 4

- **现象**
    - ![](FILES/005ACOPOS%206D常见报错处理/image-20240515231420391.png)
- **解决方式**
    - 使用PMT软件更新ACOPOS 6D控制器版本（.pmiu文件）
    - 使用此Flyway Update Tool软件重复几次更新
    - 修改Layout，几块定子几块定子分别更新。

# 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-05-15 | LYF<br>YZY | 初次创建 |
