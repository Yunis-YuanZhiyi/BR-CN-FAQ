# [VC4] Windows10环境下使用VC4出现崩溃现象
问题描述
在Windows 10环境下使用VC4出现编码器打开崩溃，AS自动关闭现象；

解决方案
根据“Supportinformation VC4 vs. Windows en”说明。
首先查看Windows 10的详细版本：按“Win+R”，输入“winver”；
VC4在Winodws 10 (Version 1803 or high) 版本中会出现崩溃现象，总部正在和微软一同着手解决该问题。
目前总部给出的解决办法如下：

1. For the time being don´t install system updates (so called „Feature Updates“) of Windows 10! "Feature updates" mainly bring new / changed functionalities and can therefore also be safely in-stalled at a later date. The installation of normal bugfixes does not need to be suspended.
2. If Windows 10 Version 1803 or higher has already been installed, you should consider uninstalling or downgrading to the previous version.
3. If the use of new Windows versions is unavoidable, an older Windows 10 version can be used by us-ing virtual environments. Practical virtualization solutions are e.g. "VMWare Workstation " or "Virtu-alBox " (free of charge from Oracle)
4. If the VC4 Editor has to be used on a newer Windows 10 version, care should be taken not to change the size of the VC4 Editor window unnecessarily. This at least minimizes the risk of crashes.

