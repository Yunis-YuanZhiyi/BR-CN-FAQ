# 现象
- 某些 SafeDesigner 和 mapp Safety版本从 Automation Studio 继承许可证状态。
- Codemeter Runtime >= 7.30a （最新版本）阻止了此功能，因此在安装最新的版本后会提示如下信息
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104144826568.png)
> 需要注意SERVOsoft v4.4需要Codemeter Runtime >= 7.40，因此在实际使用时，此问题是不兼容的。
# Codemeter Runtime可用版本信息
- Codemeter Runtime 7.21a 对应Technology Guarding版本为1.2.1.5
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150421001.png)
- 对应官网的下载链接
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150541353.png)
- [Technology Guarding](https://www.br-automation.com/zh/downloads/software/technology-guarding/technology-guarding/)

# 影响范围
## 受影响范围的SafeDesigner与mappSafety版本
- SafeDesigner 4.4.0 与 4.3.x 
- mapp Safety < 5.12.
## 不受此影响的SafeDesigner与mappSafety版本
- SafeDesigner 4.4.1
    - [Automation Studio SafeDESIGNER](https://www.br-automation.com/zh/downloads/software/safedesigner/automation-studio-safedesigner/)
- mappSafety >= 5.12

# 若不能升级SafeDesigner版本或者mappSafety版本，解决方式如下
> 简要流程：卸载Codemeter，安装Technology Guarding，AS打开报错，到Windows路径里改文件夹名字

1. 先卸载codemeter
2. 安装了Technology Guarding 1.2.1.5（其中包含的codemeter版本为7.21a）
3. 安装完，打开as会弹出如下信息
![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150944996.png)
4. 到`C:\Windows\Microsoft.NET\assembly\GAC_MSIL\WibuCmNET`路径下，
文件夹中间数字改成上图中as提示需要的版本
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104151055989.png)
```
v4.0_7.21.4611.501__01d86e1eb0c69c23 —> 
v4.0_7.51.5429.500__01d86e1eb0c69c23
```
