- 9207 由软件复位引发的PLC重启 
- 当PLC被AR自己重启时（主要是一些被触发的事件。），9207信息会被写入Logger中，例如，在冗余切换过程中CPU被切换等等。

## 触发类型
- 从Automation Studio操作
    - ![](FILES/9207%20ERR_RST_SOFTWARE/image-20230424181253086.png)
- 电源掉电
- 使用功能块SYS_Lib中的SYSreset函数
```
SYSreset(1, SYSLIB_WARMSTART);  (* perform WARMSTART *)
```

- 不同触发类型，警告会有所不同。