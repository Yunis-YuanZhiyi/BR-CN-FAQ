> Tags: #FTP #通信 #文件

- [B02.031-贝加莱FTP Server配置与相关说明](#_b02031-%E8%B4%9D%E5%8A%A0%E8%8E%B1ftp-server%E9%85%8D%E7%BD%AE%E4%B8%8E%E7%9B%B8%E5%85%B3%E8%AF%B4%E6%98%8E)
- [1 简述](#_1-%E7%AE%80%E8%BF%B0)
- [2 贝加莱文件系统说明](#_2-%E8%B4%9D%E5%8A%A0%E8%8E%B1%E6%96%87%E4%BB%B6%E7%B3%BB%E7%BB%9F%E8%AF%B4%E6%98%8E)
- [3 在Secure文件系统下，访问USER盘](#_3-%E5%9C%A8secure%E6%96%87%E4%BB%B6%E7%B3%BB%E7%BB%9F%E4%B8%8B%EF%BC%8C%E8%AE%BF%E9%97%AEuser%E7%9B%98)
- [4 在NORMAL文件系统下，访问 C - SYSTEM 盘配置方式](#_4-%E5%9C%A8normal%E6%96%87%E4%BB%B6%E7%B3%BB%E7%BB%9F%E4%B8%8B%EF%BC%8C%E8%AE%BF%E9%97%AE-c---system-%E7%9B%98%E9%85%8D%E7%BD%AE%E6%96%B9%E5%BC%8F)
- [5 关于FTP的Password原密码](#_5-%E5%85%B3%E4%BA%8Eftp%E7%9A%84password%E5%8E%9F%E5%AF%86%E7%A0%81)
	- [5.1 若不能改动原先密码，解决方式](#_51-%E8%8B%A5%E4%B8%8D%E8%83%BD%E6%94%B9%E5%8A%A8%E5%8E%9F%E5%85%88%E5%AF%86%E7%A0%81%EF%BC%8C%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# B02.031-贝加莱FTP Server配置与相关说明

# 1 简述

- 在Automation Runtime上有许多客户端和服务器功能，支持不同的网络服务和协议。
- ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227000820289.png)
    - 灰色的条目为默认关闭的服务器功能
- 从CPU和以太网接口的快捷菜单中打开配置条目。每个协议都有一个独立的配置条目，用于启用和配置相应的协议。
    - ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227000939876.png)

# 2 贝加莱文件系统说明

- 在AS4.10之后，默认的文件系统均为Secure文件系统，在AS的配置中 Module system on target 参数为SAFE。
- 不同的文件系统，FTP配置参数略有不同
- 建议使用Secure文件系统，可以有效保证系统数据的冗余备份，避免因CF卡文件异常导致系统意外停机。
- 相关对应报警可见
    - [6405](../C03_故障码问题定位/6405.md)
- ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227001452043.png)

# 3 在Secure文件系统下，访问USER盘

- Module system on target 设置为 SAFE 即启用了Secure文件系统，FTP只可访问USER盘，即F盘
- 下图中设置了USER盘的大小为60MB
- 通过以下设置，即可通过FTP直接访问
- ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227001925729.png)

# 4 在NORMAL文件系统下，访问 C - SYSTEM 盘配置方式

- 通过以下设置，即可通过FTP访问CF卡中的C盘
- ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227001811878.png)

# 5 关于FTP的Password原密码

- Password参数为加密参数，一旦输入后，没有备注，则若不记得密码则连不上
- 为了保证安全，FTP的用户密码，一但输入则自动加密，加密规则为
    - 密码使用盐进行 base64 编码，并使用 sha256 进行散列化，并取一部分结果存储在Password中
- 若有源程序，建议直接修改密码，把密码记录在Password栏右侧，用新修改的用户名密码访问
    - ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227010959830.png)

## 5.1 若不能改动原先密码，解决方式

- 若项目处在维护期，原先的FTP用户名密码可能被其他上位访问，不能修改，可考虑新建配置来解决。
- 配置保持一致，新建一个User用户，用新的用户名密码访问
- ![](FILES/031贝加莱FTP%20Server配置与相关说明/image-20231227010738444.png)

# 6 更新日志

| 日期         | 修改人 | 修改内容 |
| :--------- | :-- | :--- |
| 2023-12-27 | YZY | 初次创建 |
