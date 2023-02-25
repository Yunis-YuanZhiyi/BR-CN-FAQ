# 015APC或PPC上是否可以使用第三方CFast卡？
## 问题描述
APC或PPC上的原装Cfast坏了，是否可以使用第三方CFast卡替代？

## 解决方案
不建议使用第三方CFast卡，无法确保它们是否能在B&R设备上兼容。

## 原因
一般的CFast或者CF卡厂商会将其设定为Removable Disk模式，而这种模式下是无法支持booting操作系统的（Win7及以上版本的Windows系统才有此限制）。B&R的CFast/CF卡由OEM厂商设定为Fixed Disk模式，所以可以支持Booting操作系统。如果使用第三方CFast卡，建议提前做好相关的测试。