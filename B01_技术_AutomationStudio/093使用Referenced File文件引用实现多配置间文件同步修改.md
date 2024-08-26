> Tags: #AS #开发

- [1 093使用Referenced File文件引用实现多配置间文件同步修改](#_1-093%E4%BD%BF%E7%94%A8referenced-file%E6%96%87%E4%BB%B6%E5%BC%95%E7%94%A8%E5%AE%9E%E7%8E%B0%E5%A4%9A%E9%85%8D%E7%BD%AE%E9%97%B4%E6%96%87%E4%BB%B6%E5%90%8C%E6%AD%A5%E4%BF%AE%E6%94%B9)
- [2 操作方式](#_2-%E6%93%8D%E4%BD%9C%E6%96%B9%E5%BC%8F)
- [3 功能说明](#_3-%E5%8A%9F%E8%83%BD%E8%AF%B4%E6%98%8E)
- [4 限制](#_4-%E9%99%90%E5%88%B6)
- [5 更新日志](#_5-%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97)

# 1 093使用Referenced File文件引用实现多配置间文件同步修改

- 需求来源
    - 有些项目会不断的迭代硬件配置并不断调整组态增加模块，但在其他软件功能的相关配置完全相同，如果建立多个配置Configuration来管理，则非硬件配置的其他配置均需要在几个Configuration同时修改，这在长期的维护过程中会产生较大工作量。
- 可尝试的解决方式
    - 使用Referenced File 文件引用的方式解决，即不需要同时维护多个Configuration的配置，修改原Configuration的配置文件即可利用Referenced File机制直接同步，类似于超链接的机制。

# 2 操作方式

- <span style="background:#A0CCF6">1___</span>新建Config
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134058072.png)
- <span style="background:#A0CCF6">2___</span>将原项目中的对应配置文件删除并添加Reference
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134216904.png)
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134327762.png)
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134335953.png)
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134417830.png)
- <span style="background:#A0CCF6">3___</span>分别对Connectivity，TextSystem，UnitSystem，AccessAndSecurity，mappServices，mappView中的内容进行reference
    - ![undefined](FILES/093使用Referenced%20File文件引用实现多配置间文件同步修改/image-20240826134641075.png)
- <span style="background:#A0CCF6">4___</span>编译下载新建Config对应程序
- 注意事项
    - 正确下载Reference程序后，PLC正常RUN，mappView画面正常显示，文本系统、用户系统、mapp等功能正常运行。
    - 使用安全链程序使用差异事项
        - 🔴 若使用SLX控制器，下载Reference程序后均需要重新下载一下安全程序；
        - 若使用X20SL8100控制器，下载的Reference程序中若各模块站点号均未改变，此时不需要再重新下载安全程序，安全程序可直接运行

# 3 功能说明

> 来源：AS Help GUID 9e943fd0-8f61-4615-8c3b-c65745d45c52

> 来源：[AS在线英文帮助 → Using file references](https://help.br-automation.com/#/en/4/programming%2Fguidelines%2Fprojectorganisation_guidelines_references.html)
- Automation Studio 支持在逻辑视图（Logical View）和配置视图（Physical View）中使用文件引用。
- 这意味着对对象的引用实际上位于插入位置，而不是相应对象本身。引用指向存储文件的实际目录。
- 以下内容适用于引用对象
    - 如果被引用对象确实存在于当前项目中，则会插入相对引用。在这种情况下，相对路径总是指相对于项目目录（存放项目描述文件的地方）的路径。
    - 如果引用对象在当前项目之外，则插入绝对引用
    - 可以在参考对象属性的“Location”字段中编辑该路径
- 引用的路径规范
    - 位于项目目录中的文件：路径规范应始终被视为相对于项目根目录。项目根目录仅用“`\`"引用。
        - `\Logical\Sub1\Sub2\name.c`
    - 位于项目目录之外的文件：指定的路径总是绝对路径。
        - `C:\xxxx\…`
        - http://www.brhelp.cn/…
    - 位于当前包中的文件：未输入路径。
        - 例如“name. c”
- 建议
    - 应尽可能避免引用项目目录之外的文件。这样做弊大于利！
    - 项目目录之外的文件不会受到更改监控。例如，在变量声明文件中添加的任何变量，在文件保存后将不会出现在 SmartEdit 选择列表中。
- 👍引用的优点
    - 允许使用可在整个项目中使用的文件（声明、库）。
- 👎引用的缺点
    - 移动或复制项目目录时，不会复制项目目录之外的引用文件。
    - 引用文件不包含在项目导出中。
    - 移动引用文件时，其引用不会自动更新

# 4 限制

- 引用不适合 .h 文件
    - 因为 AnsiC 编译器的包含机制无法解决引用问题。如果在不同程序中使用了一个或多个 .h 文件，建议将它们集中到一个目录中（如全局包含目录），并将该目录标识为附加包含目录。
- 这一限制适用于所有使用 `#include` 语句包含的文件。

# 5 更新日志

| 日期         | 修改人        | 修改内容 |
| :--------- | :--------- | :--- |
| 2024-08-26 | YZY<br>CJP | 初次创建 |
