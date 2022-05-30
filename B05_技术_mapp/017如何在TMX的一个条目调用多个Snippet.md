# 017如何在TMX的一个条目调用多个Snippet
需要采用Snippet嵌套Snippet的方法
### 实现说明
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165807.png)
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165816.png)
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165827.png)
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165835.png)
### 实现效果
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165842.png)

### 问题补充
•	嵌套在Snippet定义里的数据不会在界面一直自动刷新，需要刷新mappView界面或者做到Dialog里才会刷新数据源
•	不用嵌套，OPC UA变量赋值在Binding里的界面会保持一直刷新
![Img](./FILES/017如何在TMX的一个条目调用多个Snippet.md/img-20220530165950.png)
