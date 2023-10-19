> 052如何调整 OPC UA Server 访问权限

- [1 测试信息](#1%20%E6%B5%8B%E8%AF%95%E4%BF%A1%E6%81%AF)
- [2 说明](#2%20%E8%AF%B4%E6%98%8E)
- [3 新建 OPC UA 项目，默认配置下可通过匿名方式访问](#3%20%E6%96%B0%E5%BB%BA%20OPC%20UA%20%E9%A1%B9%E7%9B%AE%EF%BC%8C%E9%BB%98%E8%AE%A4%E9%85%8D%E7%BD%AE%E4%B8%8B%E5%8F%AF%E9%80%9A%E8%BF%87%E5%8C%BF%E5%90%8D%E6%96%B9%E5%BC%8F%E8%AE%BF%E9%97%AE)
- [4 通过用户名与密码访问指定的变量](#4%20%E9%80%9A%E8%BF%87%E7%94%A8%E6%88%B7%E5%90%8D%E4%B8%8E%E5%AF%86%E7%A0%81%E8%AE%BF%E9%97%AE%E6%8C%87%E5%AE%9A%E7%9A%84%E5%8F%98%E9%87%8F)
	- [4.1 若希望不同变量被不同用户访问](#4.1%20%E8%8B%A5%E5%B8%8C%E6%9C%9B%E4%B8%8D%E5%90%8C%E5%8F%98%E9%87%8F%E8%A2%AB%E4%B8%8D%E5%90%8C%E7%94%A8%E6%88%B7%E8%AE%BF%E9%97%AE)

# 1 测试信息
- Automation Studio 4.7.7
- Automation Runtime: I4.73

# 2 说明
- 至 AR G4.93，OPC UA 仅支持匿名访问与用户名密码访问。
# 3 新建 OPC UA 项目，默认配置下可通过匿名方式访问
- 默认的用户角色系统 UserRoleSystem 配置，已默认添加 Anonymous 用户
    - ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019160745927.png)
- OPC UA 变量表中默认没有 Add Role
    - ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019155525139.png)
    - 注意：
        - ❌若 Add Role 只添加 Administer，则通过默认 Anonymous 权限的无法访问
        - ✔️若 Add Role 添加了 Everyone，则通过默认 Anonymous 权限的可以访问
- CPU 系统配置中默认
- ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019155832229.png)
- 使用 UaExpert 1.6.3 版本，使用 Anonymous 授权，即可访问
- ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019155635296.png)

# 4 通过用户名与密码访问指定的变量
- ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019181133918.png)
- ![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019181336693.png)
## 4.1 若希望不同变量被不同用户访问

![](FILES/052如何调整OPC%20UA%20Server访问权限/image-20231019181705600.png)
