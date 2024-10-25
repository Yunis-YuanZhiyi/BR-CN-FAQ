> Tags: #安全链 #SafeDesigner

- [A05.029.安全链程序下载出现Setup Mode ON](#_a05029%E5%AE%89%E5%85%A8%E9%93%BE%E7%A8%8B%E5%BA%8F%E4%B8%8B%E8%BD%BD%E5%87%BA%E7%8E%B0setup-mode-on)
- [解决方式一：修改AsSafety Basic程序](#_%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E4%BF%AE%E6%94%B9assafety-basic%E7%A8%8B%E5%BA%8F)
- [解决方式二：在SafeDESIGNER软件中调整参数](#_%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%BA%8C%EF%BC%9A%E5%9C%A8safedesigner%E8%BD%AF%E4%BB%B6%E4%B8%AD%E8%B0%83%E6%95%B4%E5%8F%82%E6%95%B0)
- [更新日志](#_%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 A05.029.安全链程序下载出现Setup Mode ON

- 下装完安全程序，发现安全PLC会先进入SetupMode，在RemoteControl面板上能看到提示并可以点击关掉
- 用AS项目中 Solutions 例程的AsSafety Basic 的 VNC画面，里面没有能关掉SetupMode的按钮。
- 有什么办法能让PLC下装完不进入SetupMode
- ![](FILES/029安全链程序下载出现Setup%20Mode%20ON/image-20241025172959907.png)

# 2 解决方式一：修改AsSafety Basic程序

- 把 safeRemoteControl 功能块替换为 safeRemoteControl_V2 功能块，并设置为 safeCMD_SETUP_MODE_DEACT。
- ![](FILES/029安全链程序下载出现Setup%20Mode%20ON/image-20241025173045076.png)

# 3 解决方式二：在SafeDESIGNER软件中调整参数

- 将 SafeDESIGNER 软件中 SafeLOGIC PLC 的参数 Activate Setup Mode on empty SafeKEY 从 YES → NO。
- ![](FILES/029安全链程序下载出现Setup%20Mode%20ON/image-20241025173121195.png)

# 4 更新日志

| 日期         | 修改人       | 修改内容 |
| :--------- | :-------- | :--- |
| 2024-10-25 | LZ<br>YZY | 初次创建 |
