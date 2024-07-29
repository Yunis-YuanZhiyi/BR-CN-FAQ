- [1 B01.066.无法打开AS项目提示为被一个不存在的AS版本打开过](#_1-b01066%E6%97%A0%E6%B3%95%E6%89%93%E5%BC%80as%E9%A1%B9%E7%9B%AE%E6%8F%90%E7%A4%BA%E4%B8%BA%E8%A2%AB%E4%B8%80%E4%B8%AA%E4%B8%8D%E5%AD%98%E5%9C%A8%E7%9A%84as%E7%89%88%E6%9C%AC%E6%89%93%E5%BC%80%E8%BF%87)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 原因](#_3-%E5%8E%9F%E5%9B%A0)
- [4 解决方式](#_4-%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F)

# 1 B01.066.无法打开AS项目提示为被一个不存在的AS版本打开过

# 2 现象

- ![](FILES/066无法打开AS项目%20提示为被一个不存在的AS版本打开过/image-20230228083338536.png)
- project has recently been edited with Automation Studio V254.0.

# 3 原因

- 程序文件夹下.apj文件被异常修改

# 4 解决方式

- 找到项目路径，查看.apj文件
- 使用Notepad++之类的软件将`AutomationStudio Version`参数修改为正常的数值（例如：4.7.7.74 SP 可参考其他正常的项目中的文件内容）
- ![](FILES/066无法打开AS项目%20提示为被一个不存在的AS版本打开过/image-20230228083457327.png)
