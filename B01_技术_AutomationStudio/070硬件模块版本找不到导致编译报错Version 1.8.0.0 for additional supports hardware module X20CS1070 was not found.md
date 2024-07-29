# B0.070.硬件模块版本找不到导致编译报错Version 1.8.0.0 for additional supports hardware module X20CS1070 was not found

- 项目编译过程中如果提示硬件模块版本找不到，解决方式有两种：
    - ✅下载所需固件版本并安装
    - ❌忽略，使用笔记本中已安装的版本
        - 固件版本之间有相互依赖关系，若随意修改版本，可能导致模块功能异常
- 若是出现<font color=#F36208><u>硬件模块版本找不到导致编译报错Version '1.8.0.0' for additional supports hardware module 'X20CP1070' was not found</u></font>问题，则只能通过下载对应硬件模块才能解决编译报错问题。
- 若项目中使用了AsIOMMAN这类切换硬件配置的功能，请注意如果可能切换的配置若用到了当前配置没有的硬件与固件版本
    - 需要在additional supports hardware module中添加相关模块，根据情况将Freeze设置为on，限定相关版本
    - ![](FILES/070硬件模块版本找不到导致编译报错Version%201.8.0.0%20for%20additional%20supports%20hardware%20module%20X20CS1070%20was%20not%20found/image-20230407235701257.png)
