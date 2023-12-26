> 039如何创建与设置mappView画面访问快捷方式

> Tags: #mappView #设置

- [1 需求](#1%20%E9%9C%80%E6%B1%82)
- [2 Windows 系统上设置方式](#2%20Windows%20%E7%B3%BB%E7%BB%9F%E4%B8%8A%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F)
	- [2.1 补充参数](#2.1%20%E8%A1%A5%E5%85%85%E5%8F%82%E6%95%B0)
	- [2.2 操作方式](#2.2%20%E6%93%8D%E4%BD%9C%E6%96%B9%E5%BC%8F)

# 1 需求

- 使用 PPC 等硬件展示 mappView 画面，需要全屏显示，消除历史记录统计，支持手势滑动等操作。
- 希望能够直接双击一个图标自动按照期望方式访问 mappView，并且可以将此快捷方式添加至自启动中。

# 2 Windows 系统上设置方式

## 2.1 补充参数

```
127.0.0.1:81 --kiosk --incognito --touch-events --allow-file-access-files
```

## 2.2 操作方式

![](FILES/039如何创建与设置mappView画面访问快捷方式/image-20230804161603234.png)
