> Tags: #SDM

# B03.010-如何查看并分析System Dump文件中的相关信息？

- 通过SDM可以生成System Dump的xml文件，其中包含了SG4控制器的系统、软件、硬件、运动控制的各种信息，以及故障记录本、Profiler等诊断文件。
- 使用Systemdump Viewer工具能够快速获取控制器的systemdump文件并可打包保存，便于故障归档和后续的故障分析。
- 如有使用需要，请通过邮件方式告知，邮箱地址为： support.cn@br-automation.com
- Systemdump Viewer的使用方式如下：
    - 1.配置已安装Systemdump Viewer的计算机的IP地址和子网掩码，使之能在线连接至目标控制器
    - 2.打开Systemdump Viewer，选择Load from PLC
        - ![Img](./FILES/010如何查看并分析System%20Dump文件中的相关信息？.md/img-20220530004102.png)
    - 3.填入目标控制的IP地址并确认，即可自动上载并显示Systemdump内容，如需保存Systemdump及其他诊断文件，可使用Export菜单导出保存
        - ![Img](./FILES/010如何查看并分析System%20Dump文件中的相关信息？.md/img-20220530004110.png)
