[TOC]
# 通用部分
## MpUserX与mapp View直接连接配合
- 用户现在可以通过mapp View使用可视化会话Visualization session登录到mapp UserX
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221142552615.png)
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221142644491.png)
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221143155634.png)
- 增加额外的功能
    - 出于安全考虑，增加对RBAC的扩展（21 CFR Part 11）
        - 密码规则
        - 用户过期
        - 密码修改要求
        - 登录尝试次数限制
        - 添加字段
    - 从RBAC模式中，提供简单接口来修改用户数据库
    - 身份验证包装器 - 连接至Active Directory

## 新的授权模式Package-based licensing
- 从mapp技术包5.12开始，可以使用基于授权包的授权模式。不需要基于技术保护的授权。这意味着授权在目标系统上运行时不被检查。但是，这并不能免除被授权人正确使用授权的义务。

- 这种授权模式区分了3种不同的授权包。这些适用于每个mapp技术包。每个目标系统需要一个授权。

- 1️⃣入门版：“入门”包提供mapp技术包的基本功能。这些组件是免费提供的。例如，mapp Services的 "入门 "包包括mapp AlarmX和mapp Recipe等组件。
- 2️⃣高级版：购买 "高级 "包后，除了基本功能外，还可以使用其他组件。
- 3️⃣终极版：购买 "终极 "包后，可以使用mapp技术包的所有功能。
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221140859911.png)
- 详情可见以下链接，下载贝加莱授权说明手册
    - [贝加莱知识库 (huashengyun.online)](https://brtechs.huashengyun.online/index.php?mod=bjl&do=file&gid=19#group&do=file&gid=19&fid=2869)
> 注意需要提前登录

# mapp View
## 进行变量Binding，自动创建相关文件并关联
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221144858522.png)
## 简体中文键盘
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221145048583.png)
## EventBinding可视化编辑器支持表达式编辑器
- 用于事件处理条件和动态表达式的表达式编辑器
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221145500784.png)
## widget libraries的文件布局结构
- 一个 widget库 可以通过添加包到一个级别来结构化。这使得它有可能将派生或复合部件组合成一个逻辑单元。
- 衍生小工具。目前可以在小工具目录中用衍生小工具的类别进行过滤。  使用 "复合 "过滤器的复合小部件。可选的属性 类别 允许自定义小组件的创建者在小组件目录中通过过滤器 "类别 "指定小组件将显示在哪个类别。可以使用现有的类别或创建新的类别。
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221151512387.png)
# mapp Services
## skyline同一类通知可显示多次
- 多次通知现在可同时显示在  mapp Skyline 中的小组件 "Skyline "上 
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221143415565.png)
- ![](FILES/mappServices+mappView%205.12更新要点/image-20221221144058066.png)
## Report可以单独指定图表的高度和宽度
## Database的python脚本开始支持 Python V3.8
