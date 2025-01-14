> Tags: #轴控

- [1 NC manager error](#_1-nc-manager-error)
- [2 原因分析](#_2-%E5%8E%9F%E5%9B%A0%E5%88%86%E6%9E%90)
- [3 尝试解决方式](#_3-%E5%B0%9D%E8%AF%95%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 NC manager error

- ![](FILES/10560%20NC%20manager%20error/image-20250114172657769.png)
- ![](FILES/10560%20NC%20manager%20error/image-20250114172740321.png)
- 短文本
    - NC manager error (see 'ASCII Data')
- 错误描述
    - NC Manager库（例如ACP10MAN、ARNC0MAN）检测到错误，因此需要报告附加文本信息。
- 问题解决建议
    - 问题的确切原因可以从几个连续记录器条目的“ASCII数据”列中包含的信息中确定。

# 2 原因分析

- 通常是某个参数表有问题，例如访问了没声明的轴。

# 3 尝试解决方式

- 重启，先不要复位，TEST 看看提示什么故障码，哪个ID引起。
- 检查参数表里哪个参数有问题。

# 4 更新日志

| 日期         | 修改人              | 修改内容 |
| :--------- | :--------------- | :--- |
| 2025-01-14 | LZ<br>LPQ<br>LFW | 初次创建 |
