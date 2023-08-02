[TOC]

# 背景

- 贝加莱PLC常被用作OPC UA Server，支持被第三方OPC UA Client访问。由于OPC UA是一种安全的通信协议，配备身份证书，防止身份被冒充，因此OPC UA Server需要创建证书，来确保自身身份。
- 第三方设备Client连接贝加莱PLC，会读取PLC的签名证书，并进行有效信息判断，若证书无效，则无法正常访问，具体的流程如下：
  - ![](FILES/047OPC%20UA创建证书/image-20221114202307025.png)

    > 关于TLS/SSL的相关信息，概念相对复杂，请自行搜索学习理解。

## 贝加莱 PLC 默认自动生成的证书不能正常使用原因

- 1. 证书有效时间不合理。自动生成证书的有效期以PLC系统时间为基准，后延10年，而PLC默认系统时间在未对时情况下，不是当前时间。
- 2.签名 算法等级低，为RSA-SHA1。
- 使用OPC UA通信，建议自己创建证书，确保通信正常。

### 影响结果

- MappView 画面上数值全部为 XX，无法正常显示
- 第三方 OPC UA Client 无法与贝加莱 OPC UA Server 建立通信
# 证书创建方式

> 贝加莱AS软件自带的证书生成有问题，请勿使用。

## 步骤一：安装UaExpert软件

- 1.6.3版本官方下载链接如下：
  - [UaExpert - Unified Automation (unified-automation.com)](https://www.unified-automation.com/downloads/opc-ua-clients/uaexpert.html)
- 蓝奏云下载链接：
  - https://wwl.lanzouy.com/i6T9i0fx8sid

## 步骤二：创建证书

- **1.** 在UA Expert软件菜单栏上，Settings -- Manage Certificates 进入证书配置页面。
- ![](FILES/047OPC%20UA创建证书/image-20221114203101021.png)
- **2.** 点击Create new Application Certificate
- ![](FILES/047OPC%20UA创建证书/image-20221114203119334.png)
- **3.** 填写相关信息
  - Bernecker + Rainer Industrie Electronik Ges.m.b.H
  - IT Infrastructure
  - Eggelsberg
  - Austria
  - AT
- 需注意，Domain Names与IP Address需要调整为连接Client的IP地址与Domain，否则会提示异常。
- ![](FILES/047OPC%20UA创建证书/image-20221114203143492.png)

## 步骤三：调整与放置证书

- **1.** 点击Open Certificate Location
- ![](FILES/047OPC%20UA创建证书/image-20221114203155735.png)
- **2.** 打开的路径下，选择上两级文件夹，找到PKI文件夹。
- ![](FILES/047OPC%20UA创建证书/image-20221114203842959.png)
- **3.** 在PKI文件夹下的own文件夹下，certs里的内容即为公钥，private中的信息即为私钥。
- 文件分别对应重命名为xxx.cer与xxx.key
- 将复制黏贴至AS项目的Configuration View下的AccessAndSecurity下的对应路径。
- ![](FILES/047OPC%20UA创建证书/image-20221114205049441.png)
- **4.** 在TransportLayerSecurity中创建SSL Configuration，类型选择OPC- UA SSL configuration。选择对应的证书与私钥。
- ![](FILES/047OPC%20UA创建证书/image-20221114205229024.png)
- **5.** 在CPU 的Configuration中，在OPC-UA System中，修改Software Certificates的选项为刚刚填写的SSLConfiguration。

![](FILES/047OPC%20UA创建证书/image-20221114205322475.png)

## 结果：使用UA Expert软件连接，证书信息正常不报错

![](FILES/047OPC%20UA创建证书/image-20221114212457108.png)
