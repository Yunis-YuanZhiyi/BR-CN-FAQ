# 001AS打开报错Could not load file or assembly 
## 问题描述
AS打开报错

Could not load file or assembly 
TechnologyGuarding.Interface， Version=1.0.0.0, Culture=neutral, PublicKeyToken=null or one of its dependencies.
The System cannot find the file specified.

## 截图
![Img](FILES/001AS打开报错Could%20not%20load%20file%20or%20assembly/img-20220713151104.png)




## 触发原因与解决方式
| 序号 | 反馈内容                                                     | 备注                                                         | 解决方案                                                     |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | 用户卸载AS4.7后把文件夹删掉，再安装AS4.8后无法打开，codemeter服务正常 | 安装最新版的codemeter，问题仍无法解决                        | 使用腾讯管家，在卸载AS后清理了系统，没有卸载codemeter，再重装后解决 |
| 2    | 在安装过AS的电脑上安装另一个版本AS时出现                     | -                                                            | 一般是因为新安装的AS中TG的启动路径和环境变量中TG的启动路径不匹配，可以通过修改环境变量来解决，可通过下文参考查看解决 |
| 3    | 安装Target For Simulink 6.3.1之后，导致原先能够使用的Automation Sudio软件全部出现此问题 | --                                                           | 可参考下文，将环境变量改回AS软件指向的地方                   |
| 4    | AS安装前，电脑安装了桌面管理软件。打开AS时，出现如图错误     | 通过桌面打开AS时，AS的启动方式默认为非管理员方式启动。右键选择，管理员运行该软件，AS可正常启动。 | 在AS 属性-高级中，修改AS的启动方式为管理员启动，解决。       |
| 5    | --                                                           | --                                                           | 贝加莱官网Download -> Software -> Technology Guarding 下载Technology Guarding 1.2.1.5版本，重新安装 |
| 6    | --                                                           | --                                                           | BR_TG_PATH没有被写入到环境变量中，人为添加即可               |
| --   | --                                                           | --                                                           | --                                                           |

## 原因分析
- AS 启动时会检查 Technology Guarding，这个过程需要调用一些函数，而这些函数存在于BR.TechnologyGuarding.Interfaces.dll 这个库文件中。该文件位于 AS 安装目录下的 AsTools 文件夹 中，找到并打开：
- ![](FILES/001AS打开报错Could%20not%20load%20file%20or%20assembly/image-20221126235547349.png)

- 打开后进入 AsTools/Technology Guarding/bin 目录可以看到如下
- ![](FILES/001AS打开报错Could%20not%20load%20file%20or%20assembly/image-20221126235601755.png)
- 如果你打开这个路径能找到这个文件，说明 AS 文件没有缺失，但是这个路径不在 AS 启动时的加载路 径中。应用程序启动时的加载路径会按以下方式去搜索：
  - 1. Windows/system32 或Windows/SysWow64 下的系统默认路径
  - 2. ASxx.exe 这个程序同一目录下的路径
  - 3. 在程序编写时指定去某个特定路径或系统环境变量中寻找 
- 如果在 AsTools 下找不到 Technology Guarding/bin/BR.TechnologyGuarding.Interfaces.dll 这说明 AS 中存在文件损坏不完整的问题了，有可能是多次安装不同路径，导致安装到了旧的目录。可以从另一台完好的电脑将 AsTools 文件夹拷贝过来替换现有的，As4.x 的这个文件夹都是可以通用的。

## 解决方法
- 到系统环境变量设置的地方，找到 BR_TG_PATH 这个环境变量，修改它的值：（不知道如何修改环境 变量请参照百度一下）
- ![](FILES/001AS打开报错Could%20not%20load%20file%20or%20assembly/image-20221126235702539.png)
- 把这个变量的值，修改为安装目录下的 AsTools/Technology Guarding 下，然后再打开 AS 就不会报 错了

