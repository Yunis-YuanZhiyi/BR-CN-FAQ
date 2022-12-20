#### 在Audit中实现OPC UA Event监控
在变量的Display Name中，可以设置Text名/ID名，来获取对应的名字
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220144953995.png)

在OPCUADescription.tmx中设置好相应的名字，比如Injection Unit
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145005558.png)


在Event.tmx中设置好ID号为19的信息，其中{&nadename}为获取Display Name的关键词
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145018606.png)


OPC UA事件的特定编号必须为19
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145030154.png)

参考帮助，进行一些额外的设置
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145042857.png)


我们需要将事件定义成OPC UA Value-changes
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145101909.png)

需要将变量的Audit Events设置成为on
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145114317.png)

最终显示结果如下
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145123448.png)

当改变语言时，如果设置了不同语言的输出信息，可以直接进行切换
![](FILES/032mapp%20Services%205.17更新_在Audit中实现OPC%20UA%20Event监控/image-20221220145133580.png)

