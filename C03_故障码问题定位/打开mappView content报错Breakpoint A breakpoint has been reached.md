> Tags: #mappView

# 打开mappView content报错Breakpoint A breakpoint has been reached

- 每次打开一个mappView content，会报错并弹出一个报错框
- `CefSharp.BrowserSubprocess.exe - EXCEPTION`
- `Breakpoint A breakpoint has been reached.`
- ![](FILES/打开mappView%20content报错Breakpoint%20A%20breakpoint%20has%20been%20reached/image-20241010133818790.png)

# 解决方式

- 无效操作：
    - 重新打开项目，重启AS
- 有效解决方式：
    - 关闭一个CefSharp.BrowserSubprocess.exe 孤儿进程，再重启AS后解决。
    - ![](FILES/打开mappView%20content报错Breakpoint%20A%20breakpoint%20has%20been%20reached/image-20241010134044452.png)

# 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-10-10 | YZY | 初次创建 |
