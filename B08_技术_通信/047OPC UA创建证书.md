> Tags: #OPC_UA #SSL #证书 #加密

- [1 047OPC UA创建证书](#_1-047opc-ua%E5%88%9B%E5%BB%BA%E8%AF%81%E4%B9%A6)
- [2 背景](#_2-%E8%83%8C%E6%99%AF)
	- [2.1 贝加莱 PLC 默认自动生成的证书不能正常使用原因](#_21-%E8%B4%9D%E5%8A%A0%E8%8E%B1-plc-%E9%BB%98%E8%AE%A4%E8%87%AA%E5%8A%A8%E7%94%9F%E6%88%90%E7%9A%84%E8%AF%81%E4%B9%A6%E4%B8%8D%E8%83%BD%E6%AD%A3%E5%B8%B8%E4%BD%BF%E7%94%A8%E5%8E%9F%E5%9B%A0)
- [3 证书创建方式](#_3-%E8%AF%81%E4%B9%A6%E5%88%9B%E5%BB%BA%E6%96%B9%E5%BC%8F)
	- [3.1 步骤一：安装UaExpert软件](#_31-%E6%AD%A5%E9%AA%A4%E4%B8%80%E5%AE%89%E8%A3%85uaexpert%E8%BD%AF%E4%BB%B6)
	- [3.2 步骤二：创建证书](#_32-%E6%AD%A5%E9%AA%A4%E4%BA%8C%E5%88%9B%E5%BB%BA%E8%AF%81%E4%B9%A6)
	- [3.3 步骤三：调整与放置证书](#_33-%E6%AD%A5%E9%AA%A4%E4%B8%89%E8%B0%83%E6%95%B4%E4%B8%8E%E6%94%BE%E7%BD%AE%E8%AF%81%E4%B9%A6)
- [4 结果：使用UA Expert软件连接，证书信息正常不报错](#_4-%E7%BB%93%E6%9E%9C%E4%BD%BF%E7%94%A8ua-expert%E8%BD%AF%E4%BB%B6%E8%BF%9E%E6%8E%A5%EF%BC%8C%E8%AF%81%E4%B9%A6%E4%BF%A1%E6%81%AF%E6%AD%A3%E5%B8%B8%E4%B8%8D%E6%8A%A5%E9%94%99)
- [5 相关信息](#_5-%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF)
- [6 更新日志](#_6-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 047OPC UA创建证书

# 2 背景

- 贝加莱PLC常被用作OPC UA Server，支持被第三方OPC UA Client访问。由于OPC UA是一种安全的通信协议，配备身份证书，防止身份被冒充，因此OPC UA Server需要创建证书，来确保自身身份。
- 第三方设备Client连接贝加莱PLC，会读取PLC的签名证书，并进行有效信息判断，若证书无效，则无法正常访问，具体的流程如下：
- ![](FILES/047OPC%20UA创建证书/image-20221114202307025.png)

> 关于TLS/SSL的相关信息，概念相对复杂，请自行搜索学习理解。

## 2.1 贝加莱 PLC 默认自动生成的证书不能正常使用原因

- **原因**
    - 默认证书有效时间不合理。
        - 自动生成证书的有效期以PLC系统时间为基准，后延10年，而PLC默认系统时间在未对时情况下，不是当前时间。
        - 例如一台全新的PLC，没有经过系统对时，时间可能为2000-01-01，则自动生成的有效证书时间到2010即过期，第三方设备连接即会提示证书失效，报错 BadCertificateTimeInvalid。
    - 默认签名的算法等级低，为RSA-SHA1。
    - 默认证书重新生成的规则相对特殊：
        - PLC的主机名（hostname）或者IP修改，PLC重新启动后将再次创建默认证书。
- **影响结果**
    - MappView 画面上数值全部为 XX，无法正常显示
    - 第三方 OPC UA Client 无法与贝加莱 OPC UA Server 建立通信
- **建议**
    - 使用OPC UA通信，并且项目批量，建议自己创建时间范围足够广证书，确保通信正常。

# 3 证书创建方式

> 贝加莱AS软件自带的证书生成较为麻烦，且有BUG，请勿使用。

## 3.1 步骤一：安装UaExpert软件

- 1.6.3版本官方下载链接如下：
    - [UaExpert - Unified Automation (unified-automation.com)](https://www.unified-automation.com/downloads/opc-ua-clients/uaexpert.html)
- 蓝奏云下载链接：
    - https://wwl.lanzouy.com/i6T9i0fx8sid

## 3.2 步骤二：创建证书

- **1__** 在UA Expert软件菜单栏上，Settings -- Manage Certificates 进入证书配置页面。
    - ![](FILES/047OPC%20UA创建证书/image-20221114203101021.png)
- **2___** 点击 Create new Application Certificate
    - ![](FILES/047OPC%20UA创建证书/image-20221114203119334.png)
- **3___** 填写相关信息
    - Bernecker + Rainer Industrie Electronik Ges.m.b.H
    - IT Infrastructure
    - Eggelsberg
    - Austria
    - AT
    - 需注意，Domain Names与IP Address需要调整为连接Client的IP地址与Domain，否则会提示异常。
    - ![](FILES/047OPC%20UA创建证书/image-20221114203143492.png)

## 3.3 步骤三：调整与放置证书

- **1___** 点击Open Certificate Location
    - ![](FILES/047OPC%20UA创建证书/image-20221114203155735.png)
- **2___** 打开的路径下，选择上两级文件夹，找到PKI文件夹。
    - ![](FILES/047OPC%20UA创建证书/image-20221114203842959.png)
- **3___** 在PKI文件夹下的own文件夹下，certs里的内容即为公钥，private中的信息即为私钥。
    - 文件分别对应重命名为xxx.cer与xxx.key
    - 将复制黏贴至AS项目的Configuration View下的AccessAndSecurity下的对应路径。
        - ![](FILES/047OPC%20UA创建证书/image-20221114205049441.png)
- **4___** 在TransportLayerSecurity中创建SSL Configuration，类型选择OPC- UA SSL configuration。选择对应的证书与私钥。
    - ![](FILES/047OPC%20UA创建证书/image-20221114205229024.png)
- **5___** 在CPU 的Configuration中，在OPC-UA System中，修改Software Certificates的选项为刚刚填写的SSLConfiguration。
    - ![](FILES/047OPC%20UA创建证书/image-20221114205322475.png)

# 4 结果：使用UA Expert软件连接，证书信息正常不报错

- ![](FILES/047OPC%20UA创建证书/image-20221114212457108.png)

# 5 相关信息

- [044mappView对接SSL加密的OPC UA服务](/B05_技术_mapp/044mappView对接SSL加密的OPC%20UA服务.md)

# 6 更新日志

| 日期         | 修改人 | 修改内容 |
| ---------- | --- | ---- |
| 2023.08.02 | YZY | 初次创建 |
