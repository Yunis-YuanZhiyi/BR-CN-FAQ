> Tags: #mappView

- [1 B01.069.如何在多层文件夹下编译mappView项目](#_1-b01069%E5%A6%82%E4%BD%95%E5%9C%A8%E5%A4%9A%E5%B1%82%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%8B%E7%BC%96%E8%AF%91mappview%E9%A1%B9%E7%9B%AE)
- [2 现象](#_2-%E7%8E%B0%E8%B1%A1)
- [3 Win10 1607下解除限制设置方式](#_3-win10-1607%E4%B8%8B%E8%A7%A3%E9%99%A4%E9%99%90%E5%88%B6%E8%AE%BE%E7%BD%AE%E6%96%B9%E5%BC%8F)
- [4 如何了解项目路径是否超长](#_4-%E5%A6%82%E4%BD%95%E4%BA%86%E8%A7%A3%E9%A1%B9%E7%9B%AE%E8%B7%AF%E5%BE%84%E6%98%AF%E5%90%A6%E8%B6%85%E9%95%BF)

# 1 B01.069.如何在多层文件夹下编译mappView项目

# 2 现象

- 将mappView项目存放在复杂或较长命名的的文件夹中，这会导致编译问题。
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205201250.png)
- Windows 将路径名总长度限制为 260 个字符，而在编译 mappView时很容易达到，这给我们开发造成很多不便，不得不改变项目的存放位置。
- 如果文件的路径字符总数超过 260，则AS项目无法编译生成或传输。存在以下选项用以解决：
    - 将项目移动到较短的项目根路径，例如放在D盘根目录下。
    - 缩短作为路径一部分的配置或 CPU 名称
    - 在 Windows 10 上，您可以禁用 260 个字符的限制。

# 3 Win10 1607下解除限制设置方式

- [Maximum Path Length Limitation - Win32 apps | Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/fileio/maximum-file-path-limitation?tabs=powershell)

# 4 如何了解项目路径是否超长

- 要识别文件夹中的路径长度，可以使用以下powershell命令。(将显示所有大于250的路径)
- 运行PowerShell，并输入 `cmd /c dir /s /b |? { $_.length -gt 250 }`
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205523075.png)
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205420757.png)
