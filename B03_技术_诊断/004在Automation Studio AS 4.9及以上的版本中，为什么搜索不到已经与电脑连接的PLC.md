# B03.004.在Automation Studio（AS）4.9及以上的版本中，为什么搜索不到已经与电脑连接的PLC？

> 推荐阅读 → [⭐023AS软件无法扫描到实际的PLC](../B01_技术_AutomationStudio/023AS软件无法扫描到实际的PLC.md)

- PLC的SNMP参数没有激活的情况下，是无法通过AS搜索到联网的硬件的。
- 解决办法：
    - 如果已知PLC的IP地址，可以通过创建新的TCP/IP连接对PLC进行直连；
    - 在PLC的ETH的configuration修改SNMP参数，设置成activated
- 注：如果网口的默认设置为deactivated，该设置下online→setting中的PLC不可见
