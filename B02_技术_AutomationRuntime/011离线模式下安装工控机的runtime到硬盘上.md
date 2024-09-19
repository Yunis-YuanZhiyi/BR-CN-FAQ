> Tags: #工控机

- [1 B02.011.离线模式下安装工控机的runtime到硬盘上](#_1-b02011%E7%A6%BB%E7%BA%BF%E6%A8%A1%E5%BC%8F%E4%B8%8B%E5%AE%89%E8%A3%85%E5%B7%A5%E6%8E%A7%E6%9C%BA%E7%9A%84runtime%E5%88%B0%E7%A1%AC%E7%9B%98%E4%B8%8A)
- [2 方式一：使用ghost克隆(< AS4.6)](#_2-%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E4%BD%BF%E7%94%A8ghost%E5%85%8B%E9%9A%86-as46)
- [3 方式二：创建USB安装盘（>= AS4.6）](#_3-%E6%96%B9%E5%BC%8F%E4%BA%8C%EF%BC%9A%E5%88%9B%E5%BB%BAusb%E5%AE%89%E8%A3%85%E7%9B%98%EF%BC%88-as46%EF%BC%89)

# 1 B02.011.离线模式下安装工控机的runtime到硬盘上

- 工控机的硬盘拆除不方便，导致无法像制作CF卡一样离线安装runtime系统和应用程序。

# 2 方式一：使用ghost克隆(< AS4.6)

- 使用AS4.5以下版本正常创建项目
- 烧卡到CF卡，或者u盘
- 设置工控机BIOS中的启动顺序
    - USB disk
    - 硬盘
- 使用winPe系统启动工控机
- 使用ghost工具软件复制CF卡或者u盘到硬盘
- 再次启动后，工控机即可正常运行runtime

# 3 方式二：创建USB安装盘（>= AS4.6）

- 使用AS4.6创建项目
- 创建USB安装盘
    - Project-->Project Installation-->Create USB Install Drive
- 设置工控机BIOS中的启动顺序
    - USB disk
    - 硬盘
- 给硬盘安装系统
    - 工控机插上u盘，上电后，会自动安装操作系统，并自动按照项目中的设置来配置以太网口地址。
- AS联机，下载项目。
