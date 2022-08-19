# 056AS无法将库添加到logical view中
## 问题
- AS无法将AsIecCon库添加到logical view里。
## 原因
- 项目文件夹里已经存在 AsIecCon库文件，但是logical view的资源显示是根据.pkg内容来的，之前项目文件夹里的AsIecCon库文件可能不是通过AS添加的，所以.pkg没有记录，则logical view无法显示，也无法再次通过AS添加同名库。  
## 解决方式
- 把项目文件夹里的AsIecCon库文件删除，通过AS软件重新添加库。