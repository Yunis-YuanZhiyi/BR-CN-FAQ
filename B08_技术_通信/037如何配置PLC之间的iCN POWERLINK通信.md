## 解决方案


配置两台PLC之间的POWERLINK通信，需要在同一个项目里进行配置，分配配置两个configuration

## iCN的配置
新建一个Configuration，选择合适的PLC（其中Config1为主站的PLC配置，新建iCN为从站PLC的配置）：
 ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135853462.png)

在PLK的Configuration中，把站点选成controlled node从站，并配置Cycle time和主站的一致。在Channel出配置需要的输入输出通道，并配置合适的NodeID：
 ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526131542293.png)


 配置一个输入，一个输出通道
 ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526132223492.png)


## 主站MN的配置
切换成主站的Configuration：
 ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135913124.png)


-选择PLK接口，在Toolbox里添加一个iCN站点
 ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135918800.png)
 右键主站的PLK选择Configuration，设置与从站相同的循环周期2000us
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526131822200.png)

右键添加进来的icn站点选择configuration，在Referenced station里选择配置好的站点

现在可以将配置选择出来，这样就对应了刚才的configuration
如果查看icn的io mapping，即可配置之前设置好的输入输出通道，进行POWERLINK数据通信

![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526132006351.png)

切换到Logical View
在右侧的Toolbox里添加一个程序，新建两个变量用于测试
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526142238881.png)


![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141802981.png)

在程序里添加自加的程序，每个周期变量累加1
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141852719.png)

配置主站的数据点

右键epl_icn选择i/o mapping
我们配置主站发送给从站CN的数据点
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141733046.png)

配置从站的数据点

切换到CN的configuration
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141930321.png)
右键PLK选择i/o mapping
添加从站CN发送给主站的数据点
![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141955384.png)


监控主站，我们可以看到收到了从站的数据

![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230526141708172.png)

监控CN从站，我们可以看到从站也收到了主站的数据