> Tags: #VC4

# 9340 Project contains Visual Component objects but no version definition

- 现象为编译时提示报错 9340
- ![](FILES/9340%20Project%20contains%20Visual%20Component%20objects%20but%20no%20version%20definition/image-20240624081113994.png)

# 原因与解决方式

- 查看Runtime Versions
    - ![](FILES/9340%20Project%20contains%20Visual%20Component%20objects%20but%20no%20version%20definition/image-20240624081136069.png)
- 错误原因: Visual Components没有关联对应的版本
    - ![](FILES/9340%20Project%20contains%20Visual%20Component%20objects%20but%20no%20version%20definition/image-20240624081159279.png)
- 选择已有的版本，点击Apply应用即可
    - ![](FILES/9340%20Project%20contains%20Visual%20Component%20objects%20but%20no%20version%20definition/image-20240624081220212.png)

# 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-06-24 | YZY | 初次创建 |
