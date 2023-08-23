# 报错信息
- Error connecting to the port number or ip address
- Error connecting to the port number or Ip address (SG 4 only - pDevice).

# 导致报错的原因
- IP 地址 + Port 端口号，已经通过 TcpOpen 申请了，又以同样的参数再次申请。
- 使用了 AsTCP 库的任务代码，进行了代码修改后在线更新
- 资源占用冲突，
    - 例如 PLC 作 ModbusTCP Slave，即使用了配置的方式开启 Slave，又使用 ModbusTCP 源码库开启了 Slave 导致了冲突。
    - 例如 PLC 开启了 OPC UA Server，默认端口是 4840，以前有个程序使用 AsTCP 实现 Server，指定的端口也是 4840，运行的时候就会报 32651。
# 详细说明与解释
- 此报错在使用 AsTCP 库时，进行 TcpOpen 时导致错误

## 接口说明

| 接口 |参数 |数据类型 |描述|
|---|---|---|---|
|IN|enable|BOOL|使能功能块|
|IN|pIfAddr|UDINT  <br>(transmitted as a pointer to STRING)|指向需要连接TCP套接字的以太网接口的IP地址。可选参数。如果指定“0”，则在所有接口上都进行“监听”。|
|IN|port|UINT|socket的端口号|
|IN|options|UDINT|打开时可设置的选项(选项按位设置;可以设置多个选项)。|
|OUT|status|UINT|功能块返回值（0代表没有错误）|
|OUT|ident|UDINT|Socket ident|

## 解释
- **IP 号 + 端口号**，组成了一个 Socket 的基本申请资源，一个资源在系统底层对应一个 ident。
- 此 ident 数值为从 1 累加的一个数值。
- 此 ident 资源创建完成后在系统底层保留，只有 TcpClose 执行了，才能释放掉此 ident 与其对应的 **IP 号 + 端口号**对应的 Socket 资源
- 如果没有释放，这个 Ident 会一直占用这个 IP + 端口号，如果再次 TcpOpen，就会报 tcpERR_SOCKET_BIND 这个错。
- 因此在线更新了使用了 AsTCP 写的程序，当任务再次初始化执行，从头开始 TcpOpen 这个**IP 号 + 端口号**，就会提示报错，若需要解决，则需要提前 TcpClose 掉原本申请的 ident.