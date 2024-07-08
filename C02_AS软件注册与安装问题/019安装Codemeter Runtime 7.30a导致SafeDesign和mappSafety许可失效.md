> Tags: #安全链 #授权
- [1 C02.019安装Codemeter Runtime 7.30a导致SafeDesign和mappSafety许可失效](#_1-c02019%E5%AE%89%E8%A3%85codemeter-runtime-730a%E5%AF%BC%E8%87%B4safedesign%E5%92%8Cmappsafety%E8%AE%B8%E5%8F%AF%E5%A4%B1%E6%95%88)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 Codemeter Runtime可用版本信息](#_3-codemeter-runtime%E5%8F%AF%E7%94%A8%E7%89%88%E6%9C%AC%E4%BF%A1%E6%81%AF)
- [4 影响范围](#_4-%E5%BD%B1%E5%93%8D%E8%8C%83%E5%9B%B4)
	- [4.1 受影响范围的SafeDesigner与mappSafety版本](#_41-%E5%8F%97%E5%BD%B1%E5%93%8D%E8%8C%83%E5%9B%B4%E7%9A%84safedesigner%E4%B8%8Emappsafety%E7%89%88%E6%9C%AC)
	- [4.2 不受此影响的SafeDesigner与mappSafety版本](#_42-%E4%B8%8D%E5%8F%97%E6%AD%A4%E5%BD%B1%E5%93%8D%E7%9A%84safedesigner%E4%B8%8Emappsafety%E7%89%88%E6%9C%AC)
- [5 若不能升级SafeDesigner版本或者mappSafety版本，解决方式如下](#_5-%E8%8B%A5%E4%B8%8D%E8%83%BD%E5%8D%87%E7%BA%A7safedesigner%E7%89%88%E6%9C%AC%E6%88%96%E8%80%85mappsafety%E7%89%88%E6%9C%AC%EF%BC%8C%E8%A7%A3%E5%86%B3%E6%96%B9%E5%BC%8F%E5%A6%82%E4%B8%8B)

# 1 C02.019安装Codemeter Runtime 7.30a导致SafeDesign和mappSafety许可失效

# 2 现象

- 某些 SafeDesigner 和 mapp Safety版本从 Automation Studio 继承许可证状态。
- Codemeter Runtime >= 7.30a （最新版本）阻止了此功能，因此在安装最新的版本后会提示如下信息
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104144826568.png)
> 需要注意SERVOsoft v4.4需要Codemeter Runtime >= 7.40，因此在实际使用时，此问题是不兼容的。

# 3 Codemeter Runtime可用版本信息

- Codemeter Runtime 7.21a 对应Technology Guarding版本为1.2.1.5
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150421001.png)
- 对应官网的下载链接
- ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150541353.png)
- [Technology Guarding](https://www.br-automation.com/zh/downloads/software/technology-guarding/technology-guarding/)

# 4 影响范围

## 4.1 受影响范围的SafeDesigner与mappSafety版本

- SafeDesigner 4.4.0 与 4.3.x 
- mapp Safety < 5.12.

## 4.2 不受此影响的SafeDesigner与mappSafety版本

- SafeDesigner 4.4.1
    - [Automation Studio SafeDESIGNER](https://www.br-automation.com/zh/downloads/software/safedesigner/automation-studio-safedesigner/)
- mappSafety >= 5.12

# 5 若不能升级SafeDesigner版本或者mappSafety版本，解决方式如下

> 简要流程：卸载Codemeter，安装Technology Guarding，AS打开报错，到Windows路径里改文件夹名字

- 1___先卸载codemeter
- 2___安装了Technology Guarding 1.2.1.5（其中包含的codemeter版本为7.21a）
- 3___安装完，打开as会弹出如下信息
    - ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104150944996.png)
- 4___到 `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\WibuCmNET` 路径下，文件夹中间数字改成上图中as提示需要的版本
    - ![](FILES/019安装Codemeter%20Runtime%207.30a导致SafeDesign和mappSafety许可失效/image-20230104151055989.png)

```
v4.0_7.21.4611.501__01d86e1eb0c69c23 —> 
v4.0_7.51.5429.500__01d86e1eb0c69c23
```
