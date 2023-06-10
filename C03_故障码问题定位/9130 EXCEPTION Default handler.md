## 现象
- 程序运行后初始化一通过，使能运行 MpAudit，CPU 进入 SERV，报出9130
## 测试验证
1. ❌关闭 audit user manager 设定，无法解决
2. ❌CPU 执行初始化更新，无法解决
3. ✅只留存 audit 单独运行，没有问题，正常运行
4. ❌在 3 号测试基础上逐步使能程序查找问题，在使能到一个485通讯程序，问题出现，查看 logger，可能有 socket 不足问题
- ![](FILES/9130%20EXCEPTION%20Default%20handler/image-20230610162445212.png)

5. ✅在 4 号测试基础上减少 audit 监控变量数量（3000 ->1000），可行

- 条数修改位置：

- ![](FILES/9130%20EXCEPTION%20Default%20handler/image-20230610162542581.png)


## 结论
- MpAudit 会占用内部通信资源，如果项目复杂，需要减少监控通道数量
- 将Audit条目数修改到1500