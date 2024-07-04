> Tags: #仿真 #Matlab #cpp

- [1 002基于MatlabSimulink生成PLC程序Automation Studio Target For Simulink](#_1-002%E5%9F%BA%E4%BA%8Ematlabsimulink%E7%94%9F%E6%88%90plc%E7%A8%8B%E5%BA%8Fautomation-studio-target-for-simulink)
- [2 使用Target For Simulink实现MBD（基于模型开发）](#_2-%E4%BD%BF%E7%94%A8target-for-simulink%E5%AE%9E%E7%8E%B0mbd%EF%BC%88%E5%9F%BA%E4%BA%8E%E6%A8%A1%E5%9E%8B%E5%BC%80%E5%8F%91%EF%BC%89)
- [3 资源与教程获取](#_3-%E8%B5%84%E6%BA%90%E4%B8%8E%E6%95%99%E7%A8%8B%E8%8E%B7%E5%8F%96)
- [4 更新日志](#_4-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 002基于MatlabSimulink生成PLC程序Automation Studio Target For Simulink

- Automation Studio Target for Simulink 为 B&R PLC 提供了从 MATLAB/Simulink 自动生成代码的接口。
- MATLAB®/Simulink® 和 Automation Studio 仿真和开发工具可让您在几分钟内从开发模型转变为生成高质量程序代码。
- 支持 C、C++ 和结构化文本语言（IEC 61131-3）。
- 使用 MATLAB® 和 Simulink® 进行基于模型的开发可提高产品质量并缩短开发时间。
- ![](FILES/002基于MatlabSimulink生成PLC程序Automation%20Studio%20Target%20For%20Simulink/image-20240704153441154.png)
- ![](FILES/002基于MatlabSimulink生成PLC程序Automation%20Studio%20Target%20For%20Simulink/image-20240704153509709.png)

# 2 使用Target For Simulink实现MBD（基于模型开发）

- 在MBD开发中用于验证控制算法模型是否满足功能一致性。
- 在整个V&V(Validation and Verification)开发流程中，是硬件/软件集成部分的主要方法。
    - ![](FILES/002基于MatlabSimulink生成PLC程序Automation%20Studio%20Target%20For%20Simulink/image-20240704154358972.png)
- 使用Embedded Coder®，我们可以运行模型的软件在环（SIL）和处理器在环（PIL）仿真。
    - 这些模拟生成顶级模型或模型一部分的源代码。 SIL模拟会在开发计算机上编译并运行生成的代码。 PIL模拟在开发计算机上交叉编译源代码，然后在目标处理器或等效指令集模拟器上下载并运行目标代码。要确定模型组件与生成的代码是否在数值上等效，需要将 SIL 和 PIL 结果与 Normal 模式结果进行比较。
- 硬件在环HIL示意图
    - 我们可以将Matlab Simulink中运行的控制器代码与模拟实际物理对象的被测对象代码分别生成至实时运行的PLC中。
    - 可使得两个PLC以实时的方式进行通信，形成不发散的闭环控制，对控制的可靠性进行充分验证。
    - ![](FILES/002基于MatlabSimulink生成PLC程序Automation%20Studio%20Target%20For%20Simulink/image-20240704155123683.png)

# 3 资源与教程获取

- 贝加莱Automation Studio Target For Simulink下载地址
    - [Automation Studio Target for Simulink | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/zh/downloads/software/simulation/libraries-for-matlabsimulink/automation-studio-target-for-simulink/)
- 贝加莱官网产品相关说明
    - [Automation Studio Target for Simulink | B&R Industrial Automation (br-automation.com)](https://www.br-automation.com/en/products/software/modeling-and-simulation/automation-studio-target-for-simulink/)
- [点击前往 → 贝加莱社区-下载中心 → 在线查看说明文档 ](https://br-community.com/downloadDis/260)

# 4 更新日志

| 日期                             | 修改人 | 修改内容 |
| :----------------------------- | :-- | :--- |
| 2024-07-04 | YZY | 初次创建 |
