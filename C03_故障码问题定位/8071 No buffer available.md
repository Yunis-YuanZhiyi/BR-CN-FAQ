### 问题描述
![](FILES/8071%20No%20buffer%20available/image-20230215101815994.png)

![](FILES/8071%20No%20buffer%20available/image-20230215101829730.png)

### 解决方案

问题原因为连续申请buffer而没有释放buffer

FRM_open正常，查看客户程序发现客户在某个循环中未给Flag信号导致创建完buffer后没有进行write，也没有释放buffer。再次执行循环后buffer满了，导致8071。
正确的顺序为FRM_gbuf → FRM_write → FRM_gbuf  / FRM_gbuf → FRM_robuf → FRM_gbuf