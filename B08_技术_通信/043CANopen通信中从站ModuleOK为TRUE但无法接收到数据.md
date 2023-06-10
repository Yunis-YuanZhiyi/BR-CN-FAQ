## 现象
- 贝加莱使用 X 20 IF 1041-1 作为主站，与第三方 CANopen 从站进行通信
- Eds 文件能够正常导入
- 通过 Automation Studio 在线可见从站的 I/O mapping 通道中，ModuleOK 为 TRUE
- 但数据无法传递
## 解决方式
- 第三方 CANopen 从站厂商将 eds 文件进行修改后，能够正常数据传递。
- ![](FILES/043CANopen通信中从站ModuleOK为TRUE但无法接收到数据/image-20230610150825218.png)

