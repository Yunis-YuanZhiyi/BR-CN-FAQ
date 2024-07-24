# A03.031.PPC3100硬件启动自动进入BIOS并提示UEFI OS has been blocked by the current security policy

# 现象

- ![](FILES/031PPC3100硬件启动自动进入BIOS并提示UEFI%20OS%20has%20been%20blocked%20by%20the%20current%20security%20policy/image-20230213125744071.png)
- 无法进入正常ARemb显示的画面，启动后提示如上弹窗
- 更换PPC3100的分体式屏幕后则正常。
- BIOS选项如下：
- ![](FILES/031PPC3100硬件启动自动进入BIOS并提示UEFI%20OS%20has%20been%20blocked%20by%20the%20current%20security%20policy/image-20230213130248343.png)

# 解决方式

- 进入BIOS
- 选择 `Administer Secure Boot`
- ![](FILES/031PPC3100硬件启动自动进入BIOS并提示UEFI%20OS%20has%20been%20blocked%20by%20the%20current%20security%20policy/image-20230213130322322.png)
- 将Enforce Secure Boot设置为Disable
- ![](FILES/031PPC3100硬件启动自动进入BIOS并提示UEFI%20OS%20has%20been%20blocked%20by%20the%20current%20security%20policy/image-20230213130351976.png)
- 按`F10` 保存配置
