# 005GateManager是什么，有什么功能？
Tags：GateManager

A：
GateManager是技术人员和机器间的中央连接平台，在两者（技术人员和机器）都拨入后即可建立连接。
使用者根据授权设置中定义的用户帐户和访问权限建立连接。拥有权限的人员可以通过门户网站轻松直观地管理用户帐户、授权	设置和机器。

贝加莱将GateManager的托管服务和软件安装程序(Linux)提供给客户，可根据客户要求进行特定的设置。
这将允许机器制造商建立一个定制化的门户，以获取现场机器的概览。

GateManager是整套远程连接系统（SiteManager、LinkManager、GateManager）中唯一一个拥有Internet端口的组件。
这意味着GateManager必须配备完全限定域名(FQDN)；当然，它的用户界面也是基于网页（web-based）的。
在这些方面，GateManager与用于托管公司网站的普通Web服务器没有什么不同。
只有使用正确的X.509证书才允许访问和连接。
自己的实例（软件映像）的管理员可以创建“域”。域用于以逻辑方式构建和细分GateManager。
每个域可以多分配一个域管理员，他的权限只能查看和管理所分配域的内容。