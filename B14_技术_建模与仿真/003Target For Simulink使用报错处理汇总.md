> Tags: #仿真 #Matlab

- [1 003Target For Simulink使用报错处理汇总](#_1-003target-for-simulink%E4%BD%BF%E7%94%A8%E6%8A%A5%E9%94%99%E5%A4%84%E7%90%86%E6%B1%87%E6%80%BB)
- [2 打开B&R Config报错 `属性 DropDownOpeningFcn 无法识别`](#_2-%E6%89%93%E5%BC%80br-config%E6%8A%A5%E9%94%99-%E5%B1%9E%E6%80%A7-dropdownopeningfcn-%E6%97%A0%E6%B3%95%E8%AF%86%E5%88%AB)
- [3 编译报错 ModifyMdlRefFile - Path not found. Delete slprj folder](#_3-%E7%BC%96%E8%AF%91%E6%8A%A5%E9%94%99-modifymdlreffile---path-not-found-delete-slprj-folder)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 003Target For Simulink使用报错处理汇总

# 2 打开B&R Config报错 `属性 DropDownOpeningFcn 无法识别`

- **报错现象**
    - ![](FILES/003Target%20For%20Simulink使用报错处理汇总/image-20240903182242576.png)
- **解决方式**
    - mex的MingW配置没有添加到环境变量中。
    - 环境变量 Variable 为 `MW_MINGW64_LOC`，Value 为`C:\mingw64`
    - ![](FILES/003Target%20For%20Simulink使用报错处理汇总/image-20240903182651719.png)

# 3 编译报错 ModifyMdlRefFile - Path not found. Delete slprj folder

- **报错现象**
    - ModifyMdlRefFile - Path not found. Delete slprj folder
    - ![](FILES/003Target%20For%20Simulink使用报错处理汇总/image-20240903182453052.png)
- **解决方式**
    - mex的MingW配置没有添加到环境变量中。
    - 环境变量 Variable 为 `MW_MINGW64_LOC`，Value 为`C:\mingw64`
    - ![](FILES/003Target%20For%20Simulink使用报错处理汇总/image-20240903182651719.png)

# 4 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-09-03 | YZY | 初次创建 |
