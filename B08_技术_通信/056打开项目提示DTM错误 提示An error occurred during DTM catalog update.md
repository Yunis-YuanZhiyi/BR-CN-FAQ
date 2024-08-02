> Tags: #DTM

- [B08.056.打开项目提示DTM错误提示An error occurred during DTM catalog update](#_b08056%E6%89%93%E5%BC%80%E9%A1%B9%E7%9B%AE%E6%8F%90%E7%A4%BAdtm%E9%94%99%E8%AF%AF%E6%8F%90%E7%A4%BAan-error-occurred-during-dtm-catalog-update)
- [解决方式一](#_%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%80)
- [解决方式二替换文件](#_%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%BA%8C%E6%9B%BF%E6%8D%A2%E6%96%87%E4%BB%B6)
- [解决方式三重装指定版本AS](#_%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E4%B8%89%E9%87%8D%E8%A3%85%E6%8C%87%E5%AE%9A%E7%89%88%E6%9C%ACas)
- [更新日志](#_%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# B08.056.打开项目提示DTM错误提示An error occurred during DTM catalog update

- 报错信息
    - An error occurred during DTM catalog update. (An item with the same key has already been added.)
    - ![](FILES/056打开项目提示DTM错误%20提示An%20error%20occurred%20during%20DTM%20catalog%20update/image-20240710180139549.png)
- 现象
    - 打开AS软件就报错，且无法编译
    - 与电脑有关，其他的人的电脑都没有这个问题，只有一个同事的电脑出现了这样的问题

# 解决方式一

- 解决方式
    - 与ACOPOS 6D 软件安装有关
    - 第一次装6D的软件后如果打开项目没有硬件树，需要手动把这个路径下面的8YFL文件删掉
    - ![](FILES/056打开项目提示DTM错误%20提示An%20error%20occurred%20during%20DTM%20catalog%20update/image-20240710180336671.png)

# 解决方式二替换文件

- 正常的DTM目录更新后，会提示正常通过，不会报错，会有如下文件提示
    - ![](FILES/056打开项目提示DTM错误%20提示An%20error%20occurred%20during%20DTM%20catalog%20update/image-20240802165611691.png)
- 若报错，则会在下方提示有相关的log文件查看报错原因
- 报错原因基本是与DTM相关文件异常有关，且不同的AS版本4.3,4.7之间一般不影响。
    - 可以尝试用他人电脑中正常的 `AS安装文件夹\ASxx\AS\Schemes\` 与 `C:\ProgramData\BR\ASxx\Hardware` 两个文件整体替换
    - ![](FILES/056打开项目提示DTM错误%20提示An%20error%20occurred%20during%20DTM%20catalog%20update/image-20240802165700638.png)

# 解决方式三重装指定版本AS

- 将出现问题的AS软件版本删除，重新安装。

# 更新日志

| 日期         | 修改人        | 修改内容    |
| :--------- | :--------- | :------ |
| 2024-07-10 | ZJY<br>YZY | 初次创建    |
| 2024-08-02 | YZY        | 更新解决方式二 |
