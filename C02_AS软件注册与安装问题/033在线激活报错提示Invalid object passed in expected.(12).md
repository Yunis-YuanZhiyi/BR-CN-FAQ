> Tags: #AS注册

- [1 C02.033.在线激活报错提示Invalid object passed in expected.(12)](#_1-c02033%E5%9C%A8%E7%BA%BF%E6%BF%80%E6%B4%BB%E6%8A%A5%E9%94%99%E6%8F%90%E7%A4%BAinvalid-object-passed-in-expected12)
- [2 原因](#_2-%E5%8E%9F%E5%9B%A0)
- [3 解决方式：离线注册](#_3-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%EF%BC%9A%E7%A6%BB%E7%BA%BF%E6%B3%A8%E5%86%8C)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 C02.033.在线激活报错提示Invalid object passed in expected.(12)

- 全球极少数用户无法通过在线授权激活许可证
- 在尝试在线激活的时候会爆出如下错误信息

```
Invalid object passed in, ':' or '}' expected. (12): {ECHNOLOGY GUARDING}

Ein ungültiges Objekt wurde übergeben. Erwartet wurde ":" oder "}". (12): {ECHNOLOGY GUARDING
```

- ![](FILES/033在线激活报错提示Invalid%20object%20passed%20in%20expected.(12)/image-20240913112515910.png)
- ![](FILES/033在线激活报错提示Invalid%20object%20passed%20in%20expected.(12)/image-20240913112629686.png)

# 2 原因

- 这是由被阻止的URL引起的防火墙问题（由于使用可能的脚本标记而被阻止，最有可能是在传递的上下文中）。

# 3 解决方式：离线注册

- AS注册
    - [020Automation Studio离线注册方法](020Automation%20Studio离线注册方法.md)
- TG注册
    - 在AS Help中 Automation Software → Technology Guarding → Technology Guarding Wizard → Operation → Offline dongle licensing
    - [点击访问 BR在线Help → Offline dongle licensing via license file](https://help.br-automation.com/#/en/4/technologyguarding%2Ftechguardassist%2Fofflinelicensefile.html)

# 4 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-09-13 | YZY | 初次创建 |
