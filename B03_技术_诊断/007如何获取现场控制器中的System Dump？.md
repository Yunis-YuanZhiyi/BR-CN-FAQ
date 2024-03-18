> Tags: #SDM #系统诊断

# B03.007-如何获取现场控制器中的System Dump？

# 推荐链接

- [008SDM数据本地诊断工具](/C07_工具/008SDM数据本地诊断工具.md)

# 获取说明

- 该功能支持AR V3.0及以上版本，在SDM功能被开启的前提下，确保控制器通过以太网和PC连接。
- 在浏览器中输入`http：//控制器IP地址/SDM`，可访问SDM界面。
    - ![Img](./FILES/007如何获取现场控制器中的System%20Dump？.md/img-20220530003934.png)
- 在SDM的起始页上找到System Dump。点击New System Dump窗口上的ok以创建一个新的System Dump。
    - 通过此SystemDump，可将PLC的诊断信息获取，打包传递到本地，方便传递给技术支持工程师，用于后续分析。
    - ![Img](./FILES/007如何获取现场控制器中的System%20Dump？.md/img-20220530003945.png)
    - ![Img](./FILES/007如何获取现场控制器中的System%20Dump？.md/img-20220530003947.png)
