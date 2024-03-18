> Tags: #TG #TechnologyGuarding

- [029打开Technology Guarding提示未能创建SSL_TLS安全通道unable to create a secure SSL TLS channel](#029%E6%89%93%E5%BC%80Technology%20Guarding%E6%8F%90%E7%A4%BA%E6%9C%AA%E8%83%BD%E5%88%9B%E5%BB%BASSL_TLS%E5%AE%89%E5%85%A8%E9%80%9A%E9%81%93unable%20to%20create%20a%20secure%20SSL%20TLS%20channel)
- [原因](#%E5%8E%9F%E5%9B%A0)
- [解决方式](#%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [更新日志](#%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# C02.029-打开Technology Guarding提示未能创建SSL_TLS安全通道unable to create a secure SSL TLS channel

- 安装了最新的 AS 4.12，但如果我运行 Technology Guarding，则会收到此错误：
    - the request was aborted: unable to create a secure SSL/TLS channel
    - the underlying connection was closed: an unexpected error occurred while sending

![](FILES/029打开Technology%20Guarding提示未能创建SSL_TLS安全通道unable%20to%20create%20a%20secure%20SSL%20TLS%20channel/image-20240315160225630.png)

![](FILES/029打开Technology%20Guarding提示未能创建SSL_TLS安全通道unable%20to%20create%20a%20secure%20SSL%20TLS%20channel/image-20240315160234547.png)

# 原因

- TG的软件版本过低
- 新版本的 AS 和最新版本的 PVI 附带了旧版本的 TG 1.3.1.1，但却无法运行。

# 解决方式

- 前往贝加莱官方网站，下载 1.4.0.3 及以上版本，然后就可以正常工作了。
    - [Technology Guarding | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/downloads/software/technology-guarding/technology-guarding/)
    - ![](FILES/029打开Technology%20Guarding提示未能创建SSL_TLS安全通道unable%20to%20create%20a%20secure%20SSL%20TLS%20channel/image-20240315160516664.png)

# 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2024-03-15 | YZY | 初次创建 |
