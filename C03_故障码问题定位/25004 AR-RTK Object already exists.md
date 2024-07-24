> Tags: #mappServices

# 25004 AR-RTK Object already exists

- 现象
    - 一旦PLC处于运行状态且mappServices相关组件已启用，可能会出现错误日志条目
        - `25004 AR-RTK: Object already exists RtkCreateTask() failed。
    - ![](FILES/25004%20AR-RTK%20Object%20already%20exists/image-20240724163912400.png)
- 影响范围
    - 这种情况并不是在每个应用程序中均发生，仅仅是有概率发生。
    - 对程序中应用中没有进一步的负面影响。
    - mapp Services 5.21.0  ~ V5.24.0
- 解决方式
    - 使用mappServices 5.24.1 及以上版本

# 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-07-24 | YZY | 初次创建 |
