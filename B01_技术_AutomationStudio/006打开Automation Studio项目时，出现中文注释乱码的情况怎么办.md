> Tags: #AS #编码

- [1 B01.006.打开Automation Studio项目时，出现中文注释乱码的情况怎么办](#_1-b01006%E6%89%93%E5%BC%80automation-studio%E9%A1%B9%E7%9B%AE%E6%97%B6%EF%BC%8C%E5%87%BA%E7%8E%B0%E4%B8%AD%E6%96%87%E6%B3%A8%E9%87%8A%E4%B9%B1%E7%A0%81%E7%9A%84%E6%83%85%E5%86%B5%E6%80%8E%E4%B9%88%E5%8A%9E)
- [2 原因](#_2-%E5%8E%9F%E5%9B%A0)
- [3 排查方式](#_3-%E6%8E%92%E6%9F%A5%E6%96%B9%E5%BC%8F)

# 1 B01.006.打开Automation Studio项目时，出现中文注释乱码的情况怎么办

- 原本正常显示中文的项目，换一台电脑后，发现原本的中文信息都变成了乱码
    - ![undefined](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/image-20240821230044621.png)

# 2 原因

- 原因一
    - 贝加莱AS软件默认支持显示的编码为ANSI，在中国则为GB2312编码，需要确认文本的编码为GB2312
- 原因二
    - 不同的Windows电脑，由于环境语言设置错误，以其他的编码显示中文文本，则会显示乱码

# 3 排查方式

- <span style="background:#F0A7D8">1___</span>首先需要确认文本的编码是正确的，没有因为被其他软件打开改过编码
- <span style="background:#F0A7D8">2___</span>用Notepad++软件打开此项目的源文件，查看右下角的编码格式，应为 GB2312。
    - ![undefined](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/image-20240821230421316.png)
    - 若不GB2312编码，先确认编码格式，能够使用Notepad++正常显示，再转换为GB2312编码（即ANSI编码）
        - ![undefined](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/image-20240821230518331.png)
- <span style="background:#F0A7D8">3___</span>调整Windows系统的语言设置
    - 从控制面板进入
        - ![Img](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/img-20220530002546.png)
        - ![Img](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/img-20220530002550.png)
    - 从设置进入
        - ![undefined](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/image-20240821231224237.png)
- <span style="background:#F0A7D8">4___</span>确认正确的地域参数设定
    - ![Img](FILES/006打开Automation%20Studio项目时，出现中文注释乱码的情况怎么办/img-20220530002554.png)
