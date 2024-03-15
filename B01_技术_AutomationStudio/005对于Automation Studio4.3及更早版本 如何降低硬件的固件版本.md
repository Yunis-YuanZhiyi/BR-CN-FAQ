> Tags: #固件版本 #AS
# 对于Automation Studio4.3及更早版本，如何降低硬件的固件版本？
- Automation Studio 4.3项目下的软件
# 实现方式
- 以X20CP1586和AS4.2为例
- 从官网下载低版本的固件安装文件。将此exe文件通过解压缩软件提取出来获得相应文件夹。
- 将该文件夹中：`…\AS4_HW_X20CP1586\$_10_\ As\Firmware\X20CP1586`
    - 换掉项目中的目标路径：`…\AS42\ AS\Firmware\X20CP1586`
- 再将该文件夹中：`…\AS4_HW_X20CP1586\$_10_\As\Hardware\Modules`
    - 替换掉目标路径：`… \AS42\AS\Hardware\Modules`
- 再重启AS即可看到固件版本已降级。