# 001VC4画面中的ALARM信息如何在机器断电后仍能保存下来？
Tags：VC4、掉电保存
A： 
	将PLC连接AS；在AS中打开Logical View/Visualization/Visu；在Visu窗口中点击Alarm Groups；
	在Alarm Groups的History中，把Persistent改成True；重新下载程序以后，ALARM信息就能掉电保持了。