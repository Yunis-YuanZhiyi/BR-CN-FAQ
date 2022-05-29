# 004OPC UA通信中，使用UASecurityPolicy_Basic256Sha256加密方式时，将client的证书添加到server的信任列表里中，无法建立安全连接，报错Bad_SecurityChecksFailed，是什么原因？
Tags：Basic256Sha256、证书、OPC UA
A： 
使用UASecurityPolicy_Basic256Sha256加密方式时，证书的最小RSA key为2048bit，因此不能在该加密方式下使用1024bit的证书

![Img](./FILES/004OPC%20UA通信中，使用UASecurityPolicy_Basic256Sha256加密方式时，将client的证书添加到server的信任列表里中，无法建立安全连接，报错Bad_Securi.md/img-20220530012028.png)
![Img](./FILES/004OPC%20UA通信中，使用UASecurityPolicy_Basic256Sha256加密方式时，将client的证书添加到server的信任列表里中，无法建立安全连接，报错Bad_Securi.md/img-20220530012031.png)
