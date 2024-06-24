> Tags: #VC4

# 7096 Mapping for Visual Component is missing or incorrect

- 编译时报错 7096
    - ![](FILES/7096%20Mapping%20for%20Visual%20Component%20is%20missing%20or%20incorrect/image-20240624082127672.png)

# 原因与解决方式

- 因项目的软件部分已放置了Visual Component 4的组件
    - ![](FILES/7096%20Mapping%20for%20Visual%20Component%20is%20missing%20or%20incorrect/image-20240624082306231.png)
- 但在对应的ETH的配置部分，没有绑定相关的参数
    - ![](FILES/7096%20Mapping%20for%20Visual%20Component%20is%20missing%20or%20incorrect/image-20240624082237603.png)
- 重新绑定参数即可解决
    - ![](FILES/7096%20Mapping%20for%20Visual%20Component%20is%20missing%20or%20incorrect/image-20240624082512243.png)

# 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-06-24 | YZY | 初次创建 |
