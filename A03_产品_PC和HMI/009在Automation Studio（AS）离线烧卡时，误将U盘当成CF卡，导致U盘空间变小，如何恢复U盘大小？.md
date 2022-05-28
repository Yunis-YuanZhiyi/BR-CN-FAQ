# 009在Automation Studio（AS）离线烧卡时，误将U盘当成CF卡，导致U盘空间变小，如何恢复U盘大小？
Tags：Offline Installation、CF卡；
A：
1. 打开Runtime Utility Center，选择Create，modify and execute projects(.pil)
2. 在Commands中选择PC CF functions/Compact Flash service functions
3. 将Number of partitions设为1；Definition of partition size选为100%，点击Execute
4. 选择误操作的U盘，即可恢复U盘原始分区信息
5. 注意，恢复后U盘中原本的数据会丢失，需要自行通过第三方软件恢复