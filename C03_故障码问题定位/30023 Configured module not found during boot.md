# 问题
- CPU 启动后进入Sever模式  
- logger日志中查看，报出30023故障
- ![](FILES/30023%20Configured%20module%20not%20found%20during%20boot/image-20230329133633932.png)

# 问题原因
- 模块监控功能未关闭，检测到 IF6.ST1 的模块不存在，CPU就会进入Sever模式  
- 模块配置错误：程序配置的是X20cDC1198，实际硬件为X20DC1198