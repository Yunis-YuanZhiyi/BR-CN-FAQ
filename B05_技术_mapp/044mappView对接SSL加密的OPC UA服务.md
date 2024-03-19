> Tags: #OPC_UA #mappView #SSL #加密

- [1 B05.044-mappView对接SSL加密的OPC UA服务](#_1-b05044-mappview%E5%AF%B9%E6%8E%A5ssl%E5%8A%A0%E5%AF%86%E7%9A%84opc-ua%E6%9C%8D%E5%8A%A1)
- [2 介绍](#_2-%E4%BB%8B%E7%BB%8D)
- [3 mappView 服务器配置步骤](#_3-mappview-%E6%9C%8D%E5%8A%A1%E5%99%A8%E9%85%8D%E7%BD%AE%E6%AD%A5%E9%AA%A4)
	- [3.1 生成 mappView 服务器证书](#_31-%E7%94%9F%E6%88%90-mappview-%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%AF%81%E4%B9%A6)
		- [3.1.1 STEP A 找到生成证书软件openssl](#_311-step-a-%E6%89%BE%E5%88%B0%E7%94%9F%E6%88%90%E8%AF%81%E4%B9%A6%E8%BD%AF%E4%BB%B6openssl)
		- [3.1.2 STEP B 准备参数文件](#_312-step-b-%E5%87%86%E5%A4%87%E5%8F%82%E6%95%B0%E6%96%87%E4%BB%B6)
		- [3.1.3 STEP C 通过CMD运行命令](#_313-step-c-%E9%80%9A%E8%BF%87cmd%E8%BF%90%E8%A1%8C%E5%91%BD%E4%BB%A4)
	- [3.2 在AS项目中放置证书](#_32-%E5%9C%A8as%E9%A1%B9%E7%9B%AE%E4%B8%AD%E6%94%BE%E7%BD%AE%E8%AF%81%E4%B9%A6)
	- [3.3 在AS项目中进行SSL 配置](#_33-%E5%9C%A8as%E9%A1%B9%E7%9B%AE%E4%B8%AD%E8%BF%9B%E8%A1%8Cssl-%E9%85%8D%E7%BD%AE)
- [4 画面显示结果](#_4-%E7%94%BB%E9%9D%A2%E6%98%BE%E7%A4%BA%E7%BB%93%E6%9E%9C)
- [5 Demo案例项目下载](#_5-demo%E6%A1%88%E4%BE%8B%E9%A1%B9%E7%9B%AE%E4%B8%8B%E8%BD%BD)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 B05.044-mappView对接SSL加密的OPC UA服务

# 2 介绍

- 默认情况下，使用贝加莱mappView技术，使用浏览器访问控制器的画面，架构示意如下，均默认没有启用传输层安全协议SSL/TLS。
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319165255833.png)
- 为了确保OPC UA与第三方客户端进行通信连接是安全的，需要将贝加莱PLC的OPC UA协议添加SSL/TLS证书，并不允许不通过传输层安全协议，明文传输数据。
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319165342412.png)
- 以下链接说明了如何自行为贝加莱的PLC的OPC UA服务器创建证书
    - [⭐047OPC UA创建证书](/B08_技术_通信/047OPC%20UA创建证书.md)
- 但一旦这样设置后，原本能正常访问的mappView画面的所有通信点都显示如下
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319165554623.png)
- 为解决此问题，需继续配置 mapp View 的证书，才能实现在浏览器上显示 OPC UA 变量值，即 mapp View server 的参数设置
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319165810331.png)

# 3 mappView 服务器配置步骤

- AS 帮助中的配置建议（GUID: 01ced6c0-28ef-4aaa-bd05-2442b971859c）
    - **SSL/TLS 1.0**（Automation Studio-4.25 及以上, Automation Runtime-A4.25 及以上）
    - **TLS 1.2**（Automation Studio-4.9及以上, Automation Runtime-A4.90及以上）

## 3.1 生成 mappView 服务器证书

### 3.1.1 STEP A 找到生成证书软件openssl

- 与OPC UA的证书生成可用UaExpert软件不同，生成mappView对应证书必须使用 **openssl.exe** 生成
- 客户证书必须包含 **authorityKeyIdentifier** 属性，并采用 DER 格式。因此，客户端证书必须使用外部工具创建，最好是 Windows 版 **openssl**。
- 使用 OpenSSL 用于创建证书（建议使用的与版本控制软件 Git 一起安装的 OpenSSL）
    - `C:\Program Files\Git\usr\bin`
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319170155812.png)

### 3.1.2 STEP B 准备参数文件

- 证书配置示例
    - 通过指定 **IP 地址** 与 OPC UA 服务器建立连接
- 在上图文件夹下创建 `ca.conf` 文件，里面内容如下，其中 IP 地址为127.0.0.1
     - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319174247258.png)
        - **注意**：keyUsage 必须包含 **keyCertSign** 参数
        - 通过**IP**与 OPC UA 服务器建立连接

```
[ req ]  
prompt = no  
distinguished_name = dn  
x509_extensions = x509v3

[ dn ]  
commonName = mapp View Server

[ x509v3 ]  
basicConstraints = critical,CA:FALSE  
subjectKeyIdentifier = hash  
authorityKeyIdentifier = keyid,issuer:always  
keyUsage = critical,nonRepudiation,digitalSignature,keyEncipherment,dataEncipherment,keyCertSign  
extendedKeyUsage = critical,serverAuth,clientAuth  
subjectAltName = URI:Client_Cpp_SDK@myComputer,IP:127.0.0.1
```

### 3.1.3 STEP C 通过CMD运行命令

- 在 win 的菜单栏中右键选 Command Prompt，在弹出的菜单中选中 Run as administrator
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240312154601422.png)
- 进入 openssl 与对应配置文件的文件夹下, 例如路径为 `C:\Program Files\Git\usr\bin`
    - 输入`CD C:\Program Files\Git\usr\bin`
        - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319174930845.png)
- 将刚刚创建好的 `ca.conf` 配置文件，放在 `C:\Temp` 文件夹下
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319175113138.png)
- 复制以下代码进命令行，按下回车键
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319175217502.png)

```
openssl.exe req -x509 -config C:\Temp\ca.conf -nodes -new -keyout C:\Temp\mappView.key -out C:\Temp\mappView.cer -sha256 -days 365 -outform DER
```

- 在 `C:\Temp\` 文件夹下，即可见生成的公钥与私钥文件
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319175342384.png)

## 3.2 在AS项目中放置证书

- 打开 AS 项目，在Configuration View 配置中的 PLC → AccessAndSecurity → CertificateStore → OwnCertificates → Certificate 和 PrivateKeys 下分别拖拽导入 <span style="background:#F0A7D8">mappView.cer</span> 和 <span style="background:#A0CCF6">mappView.key</span>
- 在 ThirdPartyCertificates → SoftwareCertificates 下导入 <span style="background:#F0A7D8">mappView.cer</span>，如下图所示。
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319175836686.png)

## 3.3 在AS项目中进行SSL 配置

- <span style="background:#F0A7D8">1___</span>必须创建新的 SSL 配置，如下图所示，在 TransportLayerSecurity 下，点击 Toolbox 中的 SSL Configuration
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319180552621.png)
- <span style="background:#F0A7D8">2___</span>双击新建配置 mappView.sslcfg，按下图所示进行配置，
    - 选择 SSL configuration type 为 OPC-UA SSL configuration
    - 在 Own certificate 下 Certificate 中选择 mappView.cer，在 Private key 中选择 mappView.key
        - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319180751651.png)
- <span style="background:#F0A7D8">3___</span>配置 mappView 服务器 OPC UA 远程连接
    - 在 Configuration View 下，点击 mappView 文件夹
    - 点击 OpcUaServer.uaserver，在下图方框相应区域中填入对应配置
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319181002309.png)
    - 完成到这一步，若不继续添加配置SSL通信第三方验证，则启动后仍然收不到数据，且在Logger中可见 **BadSecurityChecksFailed** 报错
        - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319181400334.png)
- <span style="background:#F0A7D8">4___</span>在 OPC UA的SSL配置设置中增加配置
    - 将 Validate SSL communication partner 设置为 on
    - 如下图所示，在 Config.sslcfg 下的 Trusted certificate 中选择 mappView.cer
        - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/image-20240319181929025.png)

# 4 画面显示结果

- 重新全编译项目，并开启仿真模式运行
- 显示画面如下，则代表 SSL 配置成功运行
    - ![](FILES/044mappView对接SSL加密的OPC%20UA服务/SSL1.gif)

# 5 Demo案例项目下载

- 基于AS4.12实现
- [点击下载Demo](/B05_技术_mapp/FILES/044mappView对接SSL加密的OPC%20UA服务/CertificateSSL-mappView-2024-03-19.zip ':ignore')

# 6 更新日志

| 日期         | 修改人 | 修改内容                                                                                                                                                                                                                                                                                                                                            |
| ---------- | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2024-03-13 | WKJ | 初次创建<br>基于 [UAExpert, mappView: How to make a secure OPCUA connection to OPCUA server with communication partner validation - Share Info & Ideas - B&R Community (br-automation.com)](https://community.br-automation.com/t/uaexpert-mappview-how-to-make-a-secure-opcua-connection-to-opcua-server-with-communication-partner-validation/2414) |
| 2024-03-19 | YZY | 更新优化文档                                                                                                                                                                                                                                                                                                                                          |
