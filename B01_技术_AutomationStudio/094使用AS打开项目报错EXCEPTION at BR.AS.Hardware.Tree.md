> Tags: #AS

# 1 B01.094.使用AS打开项目报错EXCEPTION at BR.AS.Hardware.Tree

- 使用AS软件打开其他人提供的AS项目，报错 EXCEPTION at: BR.AS.Hardware.Tree

```
EXCEPTION at: BR.AS.Hardware.Tree
Message:Object reference not set to an instance of an object.
CallTree:at
BR.AS.Hardware.Tree.HardwareTreeView.getCanUndo()
at
53 6()
atBR.AS.Hardware.Tree.HardwareTreeView.lsEnabled(Int32
commandld)
at 
BR.AS.Hardware.Tree.Wrapper.HardwareTreeWrapper.lsEnabled(Int32
commandId)
```

- ![](FILES/094使用AS打开项目报错EXCEPTION%20at%20BR.AS.Hardware.Tree/image-20240919131054594.png)

# 2 原因与解决方式

- 因为使用了定制版AS4.8.3.111SP，与标准版的AS项目在硬件配置方面存在差异。
- 可尝试通过AS项目中的 File → Export 导出相关代码程序与配置，再通过File → Import导入。
- 硬件配置部分若导入失败，可能需要手动配置。

# 3 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-09-19 | ZSY<br>YZY | 初次创建 |
