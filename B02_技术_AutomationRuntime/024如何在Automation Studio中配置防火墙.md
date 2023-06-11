> 背景介绍可见 [023贝加莱操作系统支持防火墙功能吗](023贝加莱操作系统支持防火墙功能吗.md)
> 详细案例可见 [025贝加莱防火墙Firewall配置案例](025贝加莱防火墙Firewall配置案例.md)

## 使用要求
- 使用 Automation Studio 4.6 及以上版本
- Automation Runtime 4.6 及以上版本
## 配置使用
- 该配置在 Configuration View 下的 Technology Package 中的 AccessAndSecurity 里进行设置。
- ![](FILES/024如何在Automation%20Studio中配置防火墙/image-20230611131514076.png)

## 新项目如何添加？
- 如果是新项目或者低版本 AS 项目升级上来的项目，可能找不到 Firewall 文件夹。
- Firewall Package 可以在 AccessAndSecurity 文件夹下右键 Add Object 添加
    - ![](FILES/024如何在Automation%20Studio中配置防火墙/image-20230611131837636.png)
    - 防火墙包只能在“AccessAndSecurity”技术包下添加。
    - 它不能被移除。
- 防火墙策略文件需要自行通过 `Add Object` 添加

- ![](FILES/024如何在Automation%20Studio中配置防火墙/image-20230611131847857.png)
    - 防火墙规则只能添加到防火墙包下。
    - 只能添加一个防火墙规则文件。
    - 可以将任意数量的防火墙规则添加到此防火墙规则文件中。


## 如何编辑防火墙规则
- ![](FILES/024如何在Automation%20Studio中配置防火墙/image-20230611132210350.png)
- 输入规则
    - 规则基本上有两种类型的输入模式。
    - Interactive mode 下，用户通过配置树中的下拉选择字段获得输入支持。根据设置的参数生成规则字符串，并显示在“Rule String”参数下。生成的规则在语法上总是正确的。
    - 如果以“Expert mode”输入规则，则不支持配置规则语法。可以在不进行语法检查的情况下输入字符串。规则字符串是否对应于有效的防火墙语法仅在 Automation Runtime 运行时检查。




