# 043AS软件提示ODBC Microsoft Access Driver Failed并且无法关闭
## 问题现象
- 出现这个弹窗，出现后就关不掉了，电脑关机重启也消不掉。
- ![Img](./FILES/043AS软件提示ODBC%20Microsoft%20Access%20Driver%20Failed并且无法关闭.md/img-20220630164355.png)
- 项目正常打开不会弹窗，只有编译的时候才会出现
- 空程序只要加入acp10的库就会出现，删掉就没事了

## 解决方式
- ![](FILES/043AS软件提示ODBC%20Microsoft%20Access%20Driver%20Failed并且无法关闭/image-20221024151731219.png)
- ![Img](./FILES/043AS软件提示ODBC%20Microsoft%20Access%20Driver%20Failed并且无法关闭.md/img-20220630164443.png)
- 取消Windows Region settings中的Beta:Use Unicode UTF-8 for worldwide language support选项。
- 并在安装AS软件后安装Office 365
