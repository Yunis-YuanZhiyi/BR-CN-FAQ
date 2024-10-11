> Tags: #OPC_UA #T50

- [1 A03.056.基于OPC UA对T50设备进行亮度调节](#_1-a03056%E5%9F%BA%E4%BA%8Eopc-ua%E5%AF%B9t50%E8%AE%BE%E5%A4%87%E8%BF%9B%E8%A1%8C%E4%BA%AE%E5%BA%A6%E8%B0%83%E8%8A%82)
- [2 类似方式也可用在PPC系列硬件上](#_2-%E7%B1%BB%E4%BC%BC%E6%96%B9%E5%BC%8F%E4%B9%9F%E5%8F%AF%E7%94%A8%E5%9C%A8ppc%E7%B3%BB%E5%88%97%E7%A1%AC%E4%BB%B6%E4%B8%8A)
- [3 更新日志](#_3-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 A03.056.基于OPC UA对T50设备进行亮度调节

- T50支持作为OPC UA Server
- 通过 OPC UA 客户端连接到T50后，就可以调用相应的OPC UA Client库完成对已有参数的数据在线读取和修改。
- 亮度调整：无限制调节亮度
    - ![](FILES/056基于OPC%20UA对T50设备进行亮度调节/image-20241011110424005.png)
- 可以设置声音的频率和持续的时间
    - ![](FILES/056基于OPC%20UA对T50设备进行亮度调节/image-20241011110523603.png)

# 2 类似方式也可用在PPC系列硬件上

- 通过在PPC上安装 ADI OPC UA Server，即可通过OPC UA 通讯的方式读写变量，控制屏幕亮度。
- [Hypervisor使用助手 > 应用案例 > Hypervisor下如何读取PPC硬按键状态](https://hypervisor.brhelp.cn/faq4.html)

# 3 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2022-02-16 | ZSY | 初次创建 |
| 2024-10-11 | YZY | 内容更新 |
