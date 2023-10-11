# 现象

我需要从客户那里更新一个模块，我创建了以下 PIL 文件：

```
Connection “/IF=tcpip /LOPO=11159 /SA=100”， “/RT=1000 /AM=* /sdt=5 /DAIP=192.168.4.1 /REPO=11159 /ANSL=1 /PT=11169”
Download “C：\REGOSYS\UpdatePLC\[VC_PwrCur.br](http://vc_pwrcur.br/)”， “ROM”
```

连接成功，模数的加载始终以 PVI 错误 # 11156 结束，该错误在手册中描述为内部错误。

# 解决方式

- 通过 RUC 文件创建传输，PIL 文件今天不再使用。

# 参考信息

- [077使用二进制包在线更新PLC程序](../B01_技术_AutomationStudio/077使用二进制包在线更新PLC程序.md)
