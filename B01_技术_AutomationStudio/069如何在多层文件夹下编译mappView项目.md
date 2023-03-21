## 现象
- 将mappView项目存放在复杂或较长命名的的文件夹中，这会导致编译问题。
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205201250.png)

- Windows 将路径名总长度限制为 260 个字符，而在编译 mappView时很容易达到，这给我们开发造成很多不便，不得不改变项目的存放位置。
  
- 如果文件的路径字符总数超过 260，则AS项目无法编译生成或传输。存在以下选项用以解决：
    -  将项目移动到较短的项目根路径，例如放在D盘根目录下。
    -  缩短作为路径一部分的配置或 CPU 名称
    -  在 Windows 10 上，您可以禁用 260 个字符的限制。

## Win10 1607下解除限制设置方式
- [Maximum Path Length Limitation - Win32 apps | Microsoft Learn](https://learn.microsoft.com/en-us/windows/win32/fileio/maximum-file-path-limitation?tabs=powershell)

## 如何了解项目路径是否超长
- 要识别文件夹中的路径长度，可以使用以下powershell命令。(将显示所有大于250的路径)
- 运行PowerShell，并输入 `cmd /c dir /s /b |? { $_.length -gt 250 }`
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205523075.png)
- ![](FILES/069如何在多层文件夹下编译mappView项目/image-20230321205420757.png)