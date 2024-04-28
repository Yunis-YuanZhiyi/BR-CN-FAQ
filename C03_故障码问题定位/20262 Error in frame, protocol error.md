# 20262 Error in frame, protocol error

# 问题描述

- 用mbus485rtu通讯的时候主站MBMaster报20262

# 解决方法

- 检查配置参数正常
    - 数据块里，配置了不可读取的寄存器地址也会返回26202
- 检查终端电阻
    - 最后是终端电阻没拨导致的
