## 解决方案

- 配置两台PLC之间的POWERLINK通信，需要在同一个项目里进行配置，分配配置两个configuration

- 新建一个Configuration，选择合适的PLC（其中Config1为主站的PLC配置，新建iCN为从站PLC的配置）：
- ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135853462.png)

- 在PLK的Configuration中，把站点选成controlled node从站，并配置Cycle time和主站的一致。在Channel出配置需要的输入输出通道，并配置合适的NodeID：
- ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135905646.png)

- 切换成主站的Configuration：
- ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135913124.png)


- 选择PLK接口，在Toolbox里添加一个iCN站点
- ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135918800.png)

- 现在可以将配置选择出来，这样就对应了刚才的configuration
- 如果查看icn的io mapping，即可配置之前设置好的输入输出通道，进行POWERLINK数据通信
- ![](FILES/037如何配置PLC之间的iCN%20POWERLINK通信/image-20230314135924333.png)
