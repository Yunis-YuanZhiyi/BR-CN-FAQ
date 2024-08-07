> Tags: #AS

# 烧卡或在线传程序时报错弹框提示 Configured directory does not exist

- 报错信息
    - ![](FILES/Configured%20directory%20does%20not%20exist%20烧卡或在线传程序时报错弹框提示/image-20240807163848150.png)
    - 弹出 invalid user directory，提示 Configured directory does not exist.
- 原因与解决方式
    - 项目在烧卡选项中启用了 Copy directory content to USER partition 功能，会在烧卡过程中将设定路径中的文件夹内容拷贝至CF卡的USER盘中。
    - 若使用他人项目，电脑本地没有设置此路径，则会提示上面的报错。
    - ![](FILES/Configured%20directory%20does%20not%20exist%20烧卡或在线传程序时报错弹框提示/image-20240807164326983.png)
    - 需要取消勾选拷贝文件选项卡或者创建对应的文件夹

# 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-08-07 | QHC<br>YZY | 初次创建 |
