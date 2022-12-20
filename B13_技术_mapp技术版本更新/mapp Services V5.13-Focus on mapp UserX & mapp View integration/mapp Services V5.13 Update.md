Link:[mapp View/mapp Services: Release information Version 5.13 - MpUserX connection to mapp View, XY Chart, Joystick, CodeBox #KNRZJ | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/zh/academy/knowledge-resource-search/mapp-view-mapp-services-release-information-version-513-mpuserx-connection-to-mapp-view-xy-chart-joystick-codebox-knrzj-1610288945022/)

重点关注mapp UserX 和 mapp View的配合使用

Q&A汇总
1.      是否可以同时登陆多个账户？

mapp UserX独立使用无法实现。在不同的面板中用不同的用户登陆可以实现该功能。

2.      当登陆失败三次后如何重置？

使用MpUserX功能块。下一版本中可以用UserList实现该功能。

3.      密码更改有什么规则？能否使用过去的密码？再次使用相同的密码会怎样？能否设置密码有效时间？

MpUserX提供配置设置“密码历史大小”。这允许我们的客户自由配置系统中存储了多少以前的密码，不允许将其用作新密码。在mappUserX中，用UserExpirationTime来定义密码的过期时间，用户在定义的时间段内未登录系统，则用户将被锁定。

4.      XY图表支持在一个X位置显示两个Y值来绘图吗？

支持的。但不支持单点显示。只支持数值类型，不支持datetime类型。

5.      能否手动设置Y轴上的点数？比如分为0,25,50,70,100？

可以。见下图。
![[Pasted image 20221220103820.png]]

Word&PPT Update Shown Follow：
![[1610288945033-en-original-1.1.pptx]]
![[1610288945036-en-original-1.1.docx]]

